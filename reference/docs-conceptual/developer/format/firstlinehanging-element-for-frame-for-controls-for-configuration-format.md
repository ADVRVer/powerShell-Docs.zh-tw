---
title: 設定之控制項的框架的 FirstLineHanging 元素（格式） |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 679c8bcb-b49d-4bb4-91f5-ea1af6c217e3
caps.latest.revision: 8
ms.openlocfilehash: 4553f95e48a2b1440c00b4951bea56376b00628a
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/05/2019
ms.locfileid: "72363167"
---
# <a name="firstlinehanging-element-for-frame-for-controls-for-configuration-format"></a>設定之控制項的框架的 FirstLineHanging 元素 (格式)

指定第一行資料向左移動的字元數。 此元素是在定義可供格式檔案中的所有視圖使用的通用控制項時使用。

Configuration 元素（格式）控制設定（format） CustomControl 元素的設定（格式）控制項專案的設定專案（格式） CustomControl 設定的 CustomEntries 元素（格式）Format） CustomEntry 元素，用於 CustomControl for 控制項的設定（Format） CustomItem 元素（適用于 CustomItem 的 configuration 框架專案設定的專案，適用于 configuration （格式） FirstLineHanging 元素的 CustomEntry）控制項適用于設定的控制項（格式）

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
|[用於設定之控制項的 CustomItem 的框架元素（格式）](./frame-element-for-customitem-for-controls-for-configuration-format.md)|定義資料的顯示方式，例如將資料向左或向右移位。|

## <a name="text-value"></a>文字值

指定您想要將資料行移到第一行的字元數。

## <a name="remarks"></a>備註

如果指定這個元素，您就無法指定 `FirstLineIndent` 元素。

## <a name="see-also"></a>另請參閱

[用於設定之控制項的 CustomItem 的框架元素（格式）](./frame-element-for-customitem-for-controls-for-configuration-format.md)

[撰寫 PowerShell 格式化檔案](./writing-a-powershell-formatting-file.md)
