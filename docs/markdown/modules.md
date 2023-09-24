[dox_generator](README.md) / Exports

# dox_generator

## Table of contents

### Interfaces

- [BaseSerializedNode](interfaces/BaseSerializedNode.md)

### Functions

- [$generateJSONFromSelectedNodes](modules.md#$generatejsonfromselectednodes)
- [$generateNodesFromSerializedNodes](modules.md#$generatenodesfromserializednodes)
- [$getHtmlContent](modules.md#$gethtmlcontent)
- [$getLexicalContent](modules.md#$getlexicalcontent)
- [$insertDataTransferForPlainText](modules.md#$insertdatatransferforplaintext)
- [$insertDataTransferForRichText](modules.md#$insertdatatransferforrichtext)
- [$insertGeneratedNodes](modules.md#$insertgeneratednodes)
- [copyToClipboard](modules.md#copytoclipboard)

## Functions

### $generateJSONFromSelectedNodes

▸ **$generateJSONFromSelectedNodes**<`SerializedNode`\>(`editor`, `selection`): `Object`

Gets the Lexical JSON of the nodes inside the provided Selection.

#### Type parameters

| Name | Type |
| :------ | :------ |
| `SerializedNode` | extends [`BaseSerializedNode`](interfaces/BaseSerializedNode.md) |

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `editor` | `LexicalEditor` | LexicalEditor to get the JSON content from. |
| `selection` | `RangeSelection` \| `NodeSelection` \| `GridSelection` | Selection to get the JSON content from. |

#### Returns

`Object`

an object with the editor namespace and a list of serializable nodes as JavaScript objects.

| Name | Type |
| :------ | :------ |
| `namespace` | `string` |
| `nodes` | `SerializedNode`[] |

#### Defined in

index.ts:515

___

### $generateNodesFromSerializedNodes

▸ **$generateNodesFromSerializedNodes**(`serializedNodes`): `LexicalNode`[]

This method takes an array of objects conforming to the BaseSeralizedNode interface and returns
an Array containing instances of the corresponding LexicalNode classes registered on the editor.
Normally, you'd get an Array of BaseSerialized nodes from [$generateJSONFromSelectedNodes](modules.md#$generatejsonfromselectednodes)

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `serializedNodes` | [`BaseSerializedNode`](interfaces/BaseSerializedNode.md)[] | an Array of objects conforming to the BaseSerializedNode interface. |

#### Returns

`LexicalNode`[]

an Array of Lexical Node objects.

#### Defined in

index.ts:545

___

### $getHtmlContent

▸ **$getHtmlContent**(`editor`): `string`

Returns the *currently selected* Lexical content as an HTML string, relying on the
logic defined in the exportDOM methods on the LexicalNode classes. Note that
this will not return the HTML content of the entire editor (unless all the content is included
in the current selection).

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `editor` | `LexicalEditor` | LexicalEditor instance to get HTML content from |

#### Returns

`string`

a string of HTML content

#### Defined in

index.ts:60

___

### $getLexicalContent

▸ **$getLexicalContent**(`editor`): ``null`` \| `string`

Returns the *currently selected* Lexical content as a JSON string, relying on the
logic defined in the exportJSON methods on the LexicalNode classes. Note that
this will not return the JSON content of the entire editor (unless all the content is included
in the current selection).

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `editor` | `LexicalEditor` | LexicalEditor instance to get the JSON content from |

#### Returns

``null`` \| `string`

#### Defined in

index.ts:87

___

### $insertDataTransferForPlainText

▸ **$insertDataTransferForPlainText**(`dataTransfer`, `selection`): `void`

Attempts to insert content of the mime-types text/plain or text/uri-list from
the provided DataTransfer object into the editor at the provided selection.
text/uri-list is only used if text/plain is not also provided.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `dataTransfer` | `DataTransfer` | an object conforming to the [DataTransfer interface] (https://html.spec.whatwg.org/multipage/dnd.html#the-datatransfer-interface) |
| `selection` | `RangeSelection` \| `GridSelection` | the selection to use as the insertion point for the content in the DataTransfer object |

#### Returns

`void`

#### Defined in

index.ts:113

___

### $insertDataTransferForRichText

▸ **$insertDataTransferForRichText**(`dataTransfer`, `selection`, `editor`): `void`

Attempts to insert content of the mime-types application/x-lexical-editor, text/html,
text/plain, or text/uri-list (in descending order of priority) from the provided DataTransfer
object into the editor at the provided selection.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `dataTransfer` | `DataTransfer` | an object conforming to the [DataTransfer interface] (https://html.spec.whatwg.org/multipage/dnd.html#the-datatransfer-interface) |
| `selection` | `RangeSelection` \| `GridSelection` | the selection to use as the insertion point for the content in the DataTransfer object |
| `editor` | `LexicalEditor` | the LexicalEditor the content is being inserted into. |

#### Returns

`void`

#### Defined in

index.ts:134

___

### $insertGeneratedNodes

▸ **$insertGeneratedNodes**(`editor`, `nodes`, `selection`): `void`

Inserts Lexical nodes into the editor using different strategies depending on
some simple selection-based heuristics. If you're looking for a generic way to
to insert nodes into the editor at a specific selection point, you probably want
lexical.$insertNodes

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `editor` | `LexicalEditor` | LexicalEditor instance to insert the nodes into. |
| `nodes` | `LexicalNode`[] | The nodes to insert. |
| `selection` | `RangeSelection` \| `GridSelection` | The selection to insert the nodes into. |

#### Returns

`void`

#### Defined in

index.ts:203

___

### copyToClipboard

▸ **copyToClipboard**(`editor`, `event`): `Promise`<`boolean`\>

Copies the content of the current selection to the clipboard in
text/plain, text/html, and application/x-lexical-editor (Lexical JSON)
formats.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `editor` | `LexicalEditor` | the LexicalEditor instance to copy content from |
| `event` | `ClipboardEvent` | the native browser ClipboardEvent to add the content to. |

#### Returns

`Promise`<`boolean`\>

#### Defined in

index.ts:574
