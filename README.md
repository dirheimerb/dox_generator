---
lexical/clipboard
Version
0.12.2
---

# Lexical WYSIWYG Editor Framwork Extenstion

> @lexical/clipboard

To install:

```bash
npm i @lexical/clipboard

yarn add @lexical/clipboard

pnpm add @lexical/clipboard
```

## Table of Contents

- [Lexical WYSIWYG Editor Framwork Extenstion](#lexical-wysiwyg-editor-framwork-extenstion)
  - [Table of Contents](#table-of-contents)
  - [Functions](#functions)
    - [$generateJSONFromSelectedNodes](#generatejsonfromselectednodes)
    - [$generateNodesFromSerializedNodes](#generatenodesfromserializednodes)
    - [$getHtmlContent](#gethtmlcontent)
    - [$getLexicalContent](#getlexicalcontent)
    - [$insertDataTransferForPlainText](#insertdatatransferforplaintext)
    - [$insertDataTransferForRichText](#insertdatatransferforrichtext)
    - [$insertGeneratedNodes](#insertgeneratednodes)
    - [copyToClipboard](#copytoclipboard)
    - [License: \[MIT\]](#license-mit)

---

## Functions

### $generateJSONFromSelectedNodes

> $generateJSONFromSelectedNodes`<SerializedNode>`(editor, selection): Object

This function retrieves the Lexical JSON of the nodes located inside the provided Selection.

- Type parameters:
  - SerializedNode: extends BaseSerializedNode

- Parameters:
  - editor: LexicalEditor — The LexicalEditor to extract the JSON content from.
  - selection: RangeSelection | NodeSelection | GridSelection — The specific selection to extract the JSON content from.
- Returns: Object containing:
  - namespace: string
  - nodes: SerializedNode[]

`Defined in index.ts:515`

### $generateNodesFromSerializedNodes

▸ $generateNodesFromSerializedNodes(serializedNodes): LexicalNode[]

This method processes an array of objects which adhere to the BaseSerializedNode interface, subsequently returning an Array containing the corresponding LexicalNode class instances registered on the editor. Typically, one would procure an Array of BaseSerialized nodes via the generateJSONFromSelectedNodes function.

- Parameters:
  - serializedNodes: BaseSerializedNode[] — An array of objects adhering to the BaseSerializedNode interface.
- Returns: LexicalNode[] - An array of Lexical Node objects.

`Defined in index.ts:545`

### $getHtmlContent

▸ $getHtmlContent(editor): string

This function retrieves the currently highlighted Lexical content as an HTML string. It relies upon the logic stipulated in the exportDOM methods of the LexicalNode classes. It is important to note that this function will not return the HTML content for the entirety of the editor unless all its content is highlighted.

- Parameters:
  - editor: LexicalEditor — The LexicalEditor instance from which the HTML content will be extracted.
- Returns: String representation of HTML content.

_Defined in index.ts:60_

### $getLexicalContent

▸ $getLexicalContent(editor): null | string

This function procures the currently highlighted Lexical content in the form of a JSON string. This extraction is reliant on the logic delineated in the exportJSON methods associated with the LexicalNode classes. One should be aware that this function will not return the JSON content of the entire editor unless the entirety of its content is highlighted.

- Parameters:
  - editor: LexicalEditor — The instance of LexicalEditor from which the JSON content will be retrieved.
- Returns: Null or a string representation of the JSON content.

`Defined in index.ts:87`

### $insertDataTransferForPlainText

▸ $insertDataTransferForPlainText(dataTransfer, selection): void

This function attempts to introduce the content of the mime-types text/plain or text/uri-list sourced from the specified DataTransfer object into the editor at the indicated selection. Notably, text/uri-list is exclusively utilized if text/plain is not provided.

- Parameters:
  - dataTransfer: DataTransfer — An object that conforms to the DataTransfer interface.
  - selection: RangeSelection | GridSelection — The intended selection for the content insertion point within the DataTransfer object.
- Returns: Void.

`Defined in index.ts:113`

### $insertDataTransferForRichText

▸ $insertDataTransferForRichText(dataTransfer, selection, editor): void

This function endeavors to introduce the content of various mime-types such as application/x-lexical-editor, text/html, text/plain, or text/uri-list (in a decreasing hierarchy of precedence) from the indicated DataTransfer object into the editor at the specified selection.

- Parameters:
  - dataTransfer: DataTransfer — An object adhering to the DataTransfer interface.
  - selection: RangeSelection | GridSelection — The intended selection for the content insertion point within the DataTransfer object.
  - editor: LexicalEditor — The LexicalEditor where the content will be introduced.
- Returns: Void.

`Defined in index.ts:134`

### $insertGeneratedNodes

▸ $insertGeneratedNodes(editor, nodes, selection): void

This function is designed to introduce Lexical nodes into the editor, leveraging varied strategies based on rudimentary selection-centric heuristics. If one's objective is to generally incorporate nodes into the editor at a specified selection juncture, the most suitable choice would be lexical.$insertNodes.

- Parameters:
  - editor: LexicalEditor — The LexicalEditor instance where the nodes will be inserted.
  - nodes: LexicalNode[] — The nodes intended for insertion
  - selection: RangeSelection | GridSelection — The intended selection for the node insertion.
Returns: Void.

`Defined in index.ts:203`

### copyToClipboard

▸ copyToClipboard(editor, event): Promise`<boolean>`

This function is engineered to copy the content of the current selection to the clipboard in formats such as text/plain, text/html, and application/x-lexical-editor (Lexical JSON).

- Parameters:
  - editor: LexicalEditor — The instance of LexicalEditor from which content will be copied.
  - event: ClipboardEvent — The inherent browser ClipboardEvent to which the content will be appended.
- Returns: Promise`<boolean>`.

`Defined in index.ts:574.`

> This documentation was generated using the [@lexical/clipboard](https://github.com/facebook/lexical/tree/main/packages/lexical-clipboard) package.

### License: [MIT]

Copyright (c) Meta Platforms, Inc. and affiliates.

This source code is licensed under the MIT license found in the
LICENSE file in the root directory of this source tree.
