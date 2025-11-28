## Open Questions

## FP-style or OO-style API

We have two dimensions in which the framework can grow: On the one hand we have
different schema types for node classes (e.g. text nodes, array nodes, union
nodes etc.) and on the other hand we have different operations that can be
performed on these nodes (e.g. insert text, select end or beginning, split node,
merge nodes etc.).

We can either have an OO-style in which each node type contains the methods /
operations for this node type:

```ts
interface NodeType {
  insertText(node: FlatNode, offset: number, text: string): void;
  merge(node: FlatNode, withNode: TreeNode): void;
  // ...
}

// schema/text.ts

const TextNodeType: NodeType = {
  insertText(node, offset, text) { ... },
  merge(node, withNode) { ... },
  // ...
}

// schema/array.ts

function createArrayNodeType(itemType: NodeType): NodeType {
  return {
    insertText(node, offset, text) { ... },
    merge(node, withNode) { ... },
    // ...
  }
}
```

Or we can have a FP-style in which the operations are defined as functions that
take the node type as an argument:

```typescript
interface NodeType {
  // schema definition only
}

interface FlatNode {
  id: string;
  type: NodeType;
  // ...
}

interface TreeNode {
  type: NodeType
  // ...
}

// operations/text.ts

function insertText(
  nodeType: NodeType,
  node: FlatNode,
  offset: number,
  text: string
): void {
  ...
}

// operations/merge.ts

function merge(
  nodeType: NodeType,
  node: FlatNode,
  withNode: TreeNode
): void {
  ...
}
```

**_Open question:_** Which style is better suited for extensibility,
maintainability, and usability of the editor core?

### Notes

- The FP-style seems to be best for the beginning since in developing the
  prototypes we start with a fixed set of node types but need to add / change
  operations frequently.
- The OO-style might be better for actually developing the editor core since by
  then the set of operations might be more stable and we can focus on
  extensibility of node types.

## Definition of node types

Currently it is still unclear what the best way is to define a node type.
Possible ways:

### Using classes for node types

Idea:

```typescript
abstract class Node {
  abstract merge(withNode: Node): void;
  abstract render(): React.ReactNode;
  // ...
}


class TextNode extends Node {
  merge(withNode: Node): void { ... }
  render(): React.ReactNode { ... }
  // ...
}
```

This was tried for example in
https://github.com/kulla/2025-08-25-editor-with-classes. However this does not
seem to be flexible enough since the node behavior cannot be easily described in
a strictly hierarchical class structure. For example the root node is a node
pointing to an another node similar to a node which wraps another node. However
for the root node some behavior is different (e.g. it cannot be deleted) or
special.

### Using configuration objects for node types

Idea:

```typescript
interface Schema {
  name: string

  // Typescript only information how the flat / tree node looks like
  _FlatNode: unknown
  _JSONValue: unknown

  // optional other information
  render?: (node: FlatNode) => React.ReactNode
}
```

Example pototype implementation: https://github.com/kulla/2025-10-28-editor
