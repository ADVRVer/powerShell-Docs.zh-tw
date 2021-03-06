---
title: View 之控制項的框架的 FirstLineHanging 元素（格式） |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 53694f08-57f7-4185-b443-1636a0918afc
caps.latest.revision: 8
ms.openlocfilehash: 387340cd9b0aae2ad0419b187d96ab4fee183d5a
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/05/2019
ms.locfileid: "72363787"
---
# <a name="firstlinehanging-element-for-frame-for-controls-for-view-format"></a>檢視之控制項的框架的 FirstLineHanging 元素 (格式)

指定第一行資料向左移動的字元數。 定義可供視圖使用的控制項時，會使用這個元素。

設定專案（格式） ViewDefinitions 元素（格式） View 元素（format） Controls 專案（格式）控制項的控制項專案（格式） CustomControl 元素，用於控制項的 View （Format） CustomEntries 元素CustomControl for View （format） CustomEntry 元素，用於 CustomEntries 的 view （format） CustomItem 元素，適用于 CustomEntry for view （format） CustomItem 元素的 view （format） Frame 元素View 控制項的框架（格式）

## <a name="syntax"></a>語法

```xml
<FirstLineHanging>NumberOfCharactersToShift</FirstLineHanging>
```

## <a name="attributes-and-elements"></a>屬性與元素

下列各節描述 `FirstLineHanging` 元素的屬性、子專案和父項目。

### <a name="attributes"></a>屬性

無。

### <a name="child-elements"></a>子元素

無。

### <a name="parent-elements"></a>父元素

|元素|描述|
|-------------|-----------------|
|[View 之控制項的 CustomItem 的框架元素（格式）](./frame-element-for-customitem-for-controls-for-view-format.md)|定義資料的顯示方式，例如將資料向左或向右移位。|

## <a name="text-value"></a>文字值

指定您想要將資料行移到第一行的字元數。

## <a name="remarks"></a>備註

如果指定這個元素，您就不能指定[FirstLineIndent](./firstlineindent-element-for-frame-for-controls-for-view-format.md)元素。

## <a name="see-also"></a>另請參閱

[View 之控制項的框架的 FirstLineIndent 元素（格式）](./firstlineindent-element-for-frame-for-controls-for-view-format.md)

[View 之控制項的 CustomItem 的框架元素（格式）](./frame-element-for-customitem-for-controls-for-view-format.md)

[撰寫 PowerShell 格式化檔案](./writing-a-powershell-formatting-file.md)
