---
title: TableControl 的 TableRowEntries 元素（格式） |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d10b68ca-256c-4c58-b503-73f7777b39ae
caps.latest.revision: 15
ms.openlocfilehash: 88de19be02de4933f892e02093403a82ccdd5788
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/05/2019
ms.locfileid: "72368147"
---
# <a name="tablerowentries-element-for-tablecontrol-format"></a>TableControl 的 TableRowEntries 元素 (格式)

定義資料表的資料列。

TableControl （格式）的設定元素（格式） ViewDefinitions 元素（格式） TableControl 元素（格式） TableRowEntries 元素

## <a name="syntax"></a>語法

```xml
<TableRowEntries>
  <TableRowEntry>...</TableRowEntry>
</TableRowEntries>
```

## <a name="attributes-and-elements"></a>屬性與元素

下列各節描述 `TableRowEntries` 專案的屬性、子專案和父項目。

### <a name="attributes"></a>屬性

無。

### <a name="child-elements"></a>子元素

|元素|描述|
|-------------|-----------------|
|[TableControl 之 TableRowEntries 的 TableRowEntry 元素（格式）](./tablerowentry-element-for-tablerowentries-for-tablecontrol-format.md)|必要項目。<br /><br /> 定義在資料表的資料列中顯示的資料。|

### <a name="parent-elements"></a>父元素

|元素|描述|
|-------------|-----------------|
|[TableControl 元素（格式）](./tablecontrol-element-format.md)|定義視圖的資料表格式。|

## <a name="remarks"></a>備註

您必須為數據表視圖指定一個或多個 `TableRowEntry` 元素。 可以新增的 `TableRowEntry` 專案數沒有最大限制，也沒有其順序重要性。

如需有關資料表視圖之元件的詳細資訊，請參閱[建立資料表視圖](./creating-a-table-view.md)。

## <a name="example"></a>範例

下列範例顯示的 `TableRowEntries` 專案會定義一個資料列，以顯示 system.servicemodel 物件的兩個屬性[值。](/dotnet/api/System.Diagnostics.Process)

```xml
<TableRowEntries>
  <TableRowEntry>
    <EntrySelectedBy>
      <TypeName>System.Diagnostics.Process</TypeName>
    </EntrySelectedBy>
    <TableColumnItems>
      <TableColumnItem>
        <PropertyName> Property for first column</PropertyName>
      </TableColumnItem>
      <TableColumnItem>
        <PropertyName> Property for second column</PropertyName>
      </TableColumnItem>
    </TableColumnItems>
  </TableRowEntry>
</TableRowEntries>

```

## <a name="see-also"></a>另請參閱

[建立資料表視圖](./creating-a-table-view.md)

[TableControl 元素（格式）](./tablecontrol-element-format.md)

[TableRowEntry 元素（格式）](./tablerowentry-element-for-tablerowentries-for-tablecontrol-format.md)

[撰寫 PowerShell 格式化檔案](./writing-a-powershell-formatting-file.md)
