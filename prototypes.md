# Prototypes

## Editor for Structured Documents

- [hackathoern-collab-oer-editor](https://github.com/kulla/hackathoern-collab-oer-editor):
  First prototype for collaborative editor for structured documents
- [2025-10-28-editor](https://github.com/kulla/2025-10-28-editor): Prototype for
  editor core with FP-style node type definitions
- [2025-11-19-experiment-with-two-editor-instances](https://github.com/kulla/2025-11-19-experiment-with-two-editor-instances):
  First experiment with using ProseMirror for rich text leaf nodes

## Check: Implementation with existing Rich Text Frameworks

### Prototype with Lexical

- Repo:
  https://github.com/kulla/2025-11-08-lexical-with-multiple-choice-exercise
- Demo:
  https://kulla.github.io/2025-11-08-lexical-with-multiple-choice-exercise/

#### Findings

- No other way than using node transformations to enforce the structure seems to
  be possible, see
  [this discussion](https://github.com/facebook/lexical/discussions/7750)

#### Limitations

- Implementing all necessary normalizations / node transformations is complex,
  especially for nested structures (see
  https://github.com/kulla/2025-11-08-lexical-with-multiple-choice-exercise/blob/a265396fc171ecd5078cff2b5a9de9c337df4276/src/plugins/exercise.tsx#L339-L589).
  Helpers are needed to simplify this task.
- Uneditable content is hard to implement in Lexical (currently CSS with
  `:before` and `content: "xyz"` is used as a workaround)

### Prototype with Prosekit (Prosemirror based)

In this prototype structured tuples are enforced in the document model / schema
of Prosemirror.

- Repo:
  https://github.com/kulla/2025-11-15-prosekit-with-multiple-choice-exercise
- Demo:
  https://kulla.github.io/2025-11-15-prosekit-with-multiple-choice-exercise/

#### Advantages

- Compared to Lexical the implementation of the necessary schema constraints and
  normalizations is simpler.

#### Limitations

- The UX is quite bad when content is copied / pasted. Also many wanted
  operations (like pressing Enter on multiple choice answers) does not work out
  of the box.
