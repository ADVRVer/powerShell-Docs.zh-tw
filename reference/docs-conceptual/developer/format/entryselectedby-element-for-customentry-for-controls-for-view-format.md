---
title: View 之控制項的 CustomEntry 的之 entryselectedby 元素（格式） |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b3d80a7d-3797-4c46-ae74-ae5cda79b24f
caps.latest.revision: 8
ms.openlocfilehash: efb20c3f2077547e6eb3cb28240512b444f9c481
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/05/2019
ms.locfileid: "72363887"
---
# <a name="entryselectedby-element-for-customentry-for-controls-for-view-format"></a>檢視之控制項的 CustomEntry 的 EntrySelectedBy 元素 (格式)

定義使用此控制項定義的 .NET 類型，或必須存在才能使用此定義的條件。 定義可供視圖使用的控制項時，會使用這個元素。

設定專案（格式） ViewDefinitions 元素（格式） View 元素（format） Controls 專案（格式）控制項的控制項專案（格式） CustomControl 元素，用於控制項的 View （Format） CustomEntries 元素CustomControl for view （format） CustomEntry 元素的 CustomEntries for view （format）之 entryselectedby 元素 for view （format）控制項的 CustomEntry 的控制項

## <a name="syntax"></a>語法

```xml
<EntrySelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <SelectionCondition>...</SelectionCondition>
</EntrySelectedBy>
```

## <a name="attributes-and-elements"></a>屬性與元素

下列各節描述 `EntrySelectedBy` 元素的屬性、子專案和父項目。 您必須為定義指定至少一個類型、選取集或選取條件。 您可以使用的子項目數目沒有上限。

### <a name="attributes"></a>屬性

無。

### <a name="child-elements"></a>子元素

|元素|描述|
|-------------|-----------------|
|[View 之控制項的之 entryselectedby 的 SelectionCondition 元素（格式）](./selectioncondition-element-for-entryselectedby-for-controls-for-view-format.md)|選擇性項目。<br /><br /> 定義必須存在才能使用此定義的條件。|
|[View 之控制項的之 entryselectedby 的 SelectionSetName 元素（格式）](./selectionsetname-element-for-entryselectedby-for-controls-for-view-format.md)|選擇性項目。<br /><br /> 指定一組使用此控制項定義的 .NET 類型。|
|[View 之控制項的之 entryselectedby 的 TypeName 元素（格式）](./typename-element-for-entryselectedby-for-controls-for-view-format.md)|選擇性項目。<br /><br /> 指定使用此控制項定義的 .NET 類型。|

### <a name="parent-elements"></a>父元素

|元素|描述|
|-------------|-----------------|
|[View 之控制項的 CustomEntries 的 CustomEntry 元素（格式）](./customentry-element-for-customentries-for-controls-for-view-format.md)|提供控制項的定義。|

## <a name="remarks"></a>備註

選取條件是用來定義要使用的定義必須存在的條件，例如當物件具有特定屬性時，或特定屬性值或腳本評估為 `true`時。 如需選取條件的詳細資訊，請參閱[定義使用視圖專案或專案時的條件](./defining-conditions-for-displaying-data.md)。

## <a name="see-also"></a>另請參閱

[View 之控制項的 CustomEntries 的 CustomEntry 元素（格式）](./customentry-element-for-customentries-for-controls-for-view-format.md)

[撰寫 PowerShell 格式化檔案](./writing-a-powershell-formatting-file.md)
