---
title: 定義用於顯示資料的條件 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c1e05821-6aec-437b-84a5-218a5727f88b
caps.latest.revision: 10
ms.openlocfilehash: 6036f30816e253b3f0c40c6b916279d0643acdb8
ms.sourcegitcommit: 17d798a041851382b406ed789097843faf37692d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2020
ms.locfileid: "83692498"
---
# <a name="defining-conditions-for-displaying-data"></a>定義用於顯示資料的條件

定義視圖或控制項所顯示的資料時，您可以指定必須存在的條件，才會顯示資料。 條件可以由特定屬性觸發，或在腳本或屬性值評估為時觸發 `true` 。 當符合選取條件時，會使用視圖或控制項的定義。

## <a name="specifying-a-selection-condition-for-a-definition"></a>指定定義的選取條件

建立視圖或控制項的定義時，會使用專案 `EntrySelectedBy` 來指定要使用定義的物件，或必須存在哪些條件，才能使用定義。 條件是由元素所指定 `SelectionCondition` 。

在下列範例中，會針對資料表視圖的定義指定選取條件。 在此範例中，只有在指定的腳本評估為時，才會使用此定義 `true` 。

```xml
<TableRowEntry>
  <EntrySelectedBy>
    <SelectionCondition>
      <ScriptBlock>ScriptToEvaluate</ScriptBlock>
    </SelectionCondition>
  </EntrySelectedBy>
  <TableColumnItems>
  </TableColumnItems>
</TableRowEntry>

```

針對視圖或控制項的定義，您可以指定的選取條件數目沒有限制。 唯一的需求如下：

- 選取條件必須指定一個屬性名稱或腳本來觸發條件，但不能同時指定兩者。

- 選取條件可以指定任意數目的 .NET 類型或選擇集，但無法同時指定兩者。

## <a name="specifying-a-selection-condition-for-an-item"></a>指定專案的選取條件

您也可以在專案定義中包含元素，以指定何時使用清單視圖或控制項的專案 `ItemSelectionCondition` 。 在下列範例中，會為清單視圖的專案指定選取條件。 在此範例中，只有在將腳本評估為時，才會使用此專案 `true` 。

```xml
<ListItem>
  <ItemSelectionCondition>
    <ScriptBlock>ScriptToEvaluate</ScriptBlock>
  </ItemSelectionCondition>
</ListItem>

```

您只能為一個專案指定一個選取條件。 而且條件必須指定一個屬性名稱或腳本來觸發條件，但不能同時指定這兩者。

## <a name="xml-elements"></a>XML 元素

 下列 XML 元素可用來建立選取條件。

- 下列元素會指定視圖定義的選取條件：

  - [TableControl 之 EntrySelectedBy 的 SelectionCondition 元素 (格式)](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)

  - [ListControl 之 EntrySelectedBy 的 SelectionCondition 元素 (格式)](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)

  - [WideControl 之 EntrySelectedBy 的 SelectionCondition 元素 (格式)](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)

  - [CustomControl 之 EntrySelectedBy 的 SelectionCondition 元素 (格式)](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)

- 下列專案會指定通用和視圖控制項定義的選取條件：

  - [設定之控制項的 EntrySelectedBy 的 SelectionCondition 元素 (格式)](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)

  - [檢視之控制項的 EntrySelectedBy 的 SelectionCondition 元素 (格式)](./selectioncondition-element-for-entryselectedby-for-controls-for-view-format.md)

- 下列元素會指定展開集合物件的選取條件：

  - [EnumerableExpansion 之 EntrySelectedBy 的 SelectionCondition 元素 (格式)](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)

- 下列元素會指定用於顯示新資料群組的選取條件：

  - [GroupBy 之 EntrySelectedBy 的 SelectionCondition 元素 (格式)](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)

- 下列元素指定清單視圖的專案選取條件：

  - [ListControl 之 ListItem 的 ItemSelectionCondition 元素 (格式)](./itemselectioncondition-element-for-listitem-for-listcontrol-format.md)

- 下列元素會指定控制項的專案選取條件：

  - [設定之控制項的 ExpressionBinding 的 ItemSelectionCondition 元素 (格式)](./itemselectioncondition-element-for-expressionbinding-for-controls-for-configuration-format.md)

  - [檢視之控制項的 ExpressionBinding 的 ItemSelectionCondition 元素 (格式)](./itemselectioncondition-element-for-expressionbinding-for-controls-for-view-format.md)

  - [CustomControl 之 ExpressionBinding 的 ItemSelectionCondition 元素 (格式)](./itemselectioncondition-element-for-expressionbinding-for-customcontrol-format.md)

## <a name="see-also"></a>另請參閱

[撰寫 PowerShell 格式設定檔案](./writing-a-powershell-formatting-file.md)
