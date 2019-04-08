---
title: ItemSelectionCondition ExpressionBinding 組態 （格式） 的控制項的項目 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fd3ddc33-b21c-4464-b3f2-a78dbe0062a8
caps.latest.revision: 8
ms.openlocfilehash: 4865d716ebe0460b662253a3019e93e82428b882
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/03/2019
ms.locfileid: "56861684"
---
# <a name="itemselectioncondition-element-for-expressionbinding-for-controls-for-configuration-format"></a><span data-ttu-id="c24af-102">設定之控制項的 ExpressionBinding 的 ItemSelectionCondition 元素 (格式)</span><span class="sxs-lookup"><span data-stu-id="c24af-102">ItemSelectionCondition Element for ExpressionBinding for Controls for Configuration (Format)</span></span>

<span data-ttu-id="c24af-103">定義要使用這個控制項必須存在的條件。</span><span class="sxs-lookup"><span data-stu-id="c24af-103">Defines the condition that must exist for this control to be used.</span></span> <span data-ttu-id="c24af-104">定義可供的格式化檔案中的所有檢視通用控制項時，會都使用這個項目。</span><span class="sxs-lookup"><span data-stu-id="c24af-104">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="c24af-105">組態 （格式） 的組態 （格式） 的組態 （CustomControl 的 CustomEntries 項目控制項的組態 （格式） CustomControl 項目控制項的控制項項目的組態項目 （格式） 的控制項項目CustomControl CustomEntry CustomItem 組態 （格式） 的控制項設定 ExpressionBinding 元素的控制項的組態 （格式） CustomItem 元素的控制項的格式） CustomEntry 項目ItemSelectionCondition ExpressionBinding 組態 （格式） 的控制項的項目</span><span class="sxs-lookup"><span data-stu-id="c24af-105">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) CustomItem Element for CustomEntry for Controls for Configuration ExpressionBinding Element for CustomItem for Controls for Configuration (Format) ItemSelectionCondition Element for ExpressionBinding for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="c24af-106">語法</span><span class="sxs-lookup"><span data-stu-id="c24af-106">Syntax</span></span>

```xml
<ItemSelectionCondition>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</ItemSelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="c24af-107">屬性與元素</span><span class="sxs-lookup"><span data-stu-id="c24af-107">Attributes and Elements</span></span>

<span data-ttu-id="c24af-108">下列各節說明屬性、 子項目和父項目`ItemSelectionCondition`項目。</span><span class="sxs-lookup"><span data-stu-id="c24af-108">The following sections describe attributes, child elements, and the parent element of the `ItemSelectionCondition` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="c24af-109">屬性</span><span class="sxs-lookup"><span data-stu-id="c24af-109">Attributes</span></span>

<span data-ttu-id="c24af-110">無。</span><span class="sxs-lookup"><span data-stu-id="c24af-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="c24af-111">子元素</span><span class="sxs-lookup"><span data-stu-id="c24af-111">Child Elements</span></span>

|<span data-ttu-id="c24af-112">元素</span><span class="sxs-lookup"><span data-stu-id="c24af-112">Element</span></span>|<span data-ttu-id="c24af-113">描述</span><span class="sxs-lookup"><span data-stu-id="c24af-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="c24af-114">PropertyName ItemSelectionCondition 組態 （格式） 的控制項的項目</span><span class="sxs-lookup"><span data-stu-id="c24af-114">PropertyName Element for ItemSelectionCondition for Controls for Configuration (Format)</span></span>](./propertyname-element-for-itemseclectioncondition-for-controls-for-configuration-format.md)|<span data-ttu-id="c24af-115">選擇性的項目。</span><span class="sxs-lookup"><span data-stu-id="c24af-115">Optional element.</span></span><br /><br /> <span data-ttu-id="c24af-116">指定觸發條件的.NET 屬性。</span><span class="sxs-lookup"><span data-stu-id="c24af-116">Specifies the .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="c24af-117">ScriptBlock ItemSelectionCondition 組態 （格式） 的控制項的項目</span><span class="sxs-lookup"><span data-stu-id="c24af-117">ScriptBlock Element for ItemSelectionCondition for Controls for Configuration (Format)</span></span>](./scriptblock-element-for-itemseclectioncondition-for-controls-for-configuration-format.md)|<span data-ttu-id="c24af-118">選擇性的項目。</span><span class="sxs-lookup"><span data-stu-id="c24af-118">Optional element.</span></span><br /><br /> <span data-ttu-id="c24af-119">指定的指令碼，就會觸發條件。</span><span class="sxs-lookup"><span data-stu-id="c24af-119">Specifies the script that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="c24af-120">父元素</span><span class="sxs-lookup"><span data-stu-id="c24af-120">Parent Elements</span></span>

|<span data-ttu-id="c24af-121">元素</span><span class="sxs-lookup"><span data-stu-id="c24af-121">Element</span></span>|<span data-ttu-id="c24af-122">描述</span><span class="sxs-lookup"><span data-stu-id="c24af-122">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="c24af-123">ExpressionBinding CustomItem 組態 （格式） 的控制項的項目</span><span class="sxs-lookup"><span data-stu-id="c24af-123">ExpressionBinding Element for CustomItem for Controls for Configuration (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)|<span data-ttu-id="c24af-124">定義控制項所顯示的資料。</span><span class="sxs-lookup"><span data-stu-id="c24af-124">Defines the data that is displayed by the control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="c24af-125">備註</span><span class="sxs-lookup"><span data-stu-id="c24af-125">Remarks</span></span>

<span data-ttu-id="c24af-126">您可以指定一個屬性名稱或用於這種狀況的指令碼，但不能同時指定。</span><span class="sxs-lookup"><span data-stu-id="c24af-126">You can specify one property name or a script for this condition but cannot specify both.</span></span>

## <a name="see-also"></a><span data-ttu-id="c24af-127">另請參閱</span><span class="sxs-lookup"><span data-stu-id="c24af-127">See Also</span></span>

[<span data-ttu-id="c24af-128">PropertyName ItemSelectionCondition 組態 （格式） 的控制項的項目</span><span class="sxs-lookup"><span data-stu-id="c24af-128">PropertyName Element for ItemSelectionCondition for Controls for Configuration (Format)</span></span>](./propertyname-element-for-itemseclectioncondition-for-controls-for-configuration-format.md)

[<span data-ttu-id="c24af-129">ScriptBlock ItemSelectionCondition 組態 （格式） 的控制項的項目</span><span class="sxs-lookup"><span data-stu-id="c24af-129">ScriptBlock Element for ItemSelectionCondition for Controls for Configuration (Format)</span></span>](./scriptblock-element-for-itemseclectioncondition-for-controls-for-configuration-format.md)

[<span data-ttu-id="c24af-130">ExpressionBinding CustomItem 組態 （格式） 的控制項的項目</span><span class="sxs-lookup"><span data-stu-id="c24af-130">ExpressionBinding Element for CustomItem for Controls for Configuration (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)

[<span data-ttu-id="c24af-131">撰寫 PowerShell 格式化檔案</span><span class="sxs-lookup"><span data-stu-id="c24af-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)