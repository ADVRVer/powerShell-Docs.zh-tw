---
title: CustomControl 檢視 （格式） 的 CustomEntry CustomItem 項目 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 98708c1d-6f39-4a76-b454-31153a6ade8c
caps.latest.revision: 12
ms.openlocfilehash: 3c110bd5fe3ef2f790ef136556afa7c29d0b5b29
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/03/2019
ms.locfileid: "56856184"
---
# <a name="customitem-element-for-customentry-for-customcontrol-for-view-format"></a><span data-ttu-id="dfeae-102">檢視之 CustomControl 的 CustomEntry 的 CustomItem 元素 (格式)</span><span class="sxs-lookup"><span data-stu-id="dfeae-102">CustomItem Element for CustomEntry for CustomControl for View (Format)</span></span>

<span data-ttu-id="dfeae-103">定義自訂的控制項檢視所顯示的資料和顯示方式。</span><span class="sxs-lookup"><span data-stu-id="dfeae-103">Defines what data is displayed by the custom control view and how it is displayed.</span></span> <span data-ttu-id="dfeae-104">定義自訂控制項的檢視時，會使用這個項目。</span><span class="sxs-lookup"><span data-stu-id="dfeae-104">This element is used when defining a custom control view.</span></span>

<span data-ttu-id="dfeae-105">組態項目 （格式） ViewDefinitions 項目 （格式） 檢視項目 （格式） CustomControl 項目 （格式） CustomEntries 項目 CustomControl CustomEntries 用於檢視 （格式） CustomItem 元素的檢視 （格式） CustomEntry 元素CustomEntry 檢視 （格式）</span><span class="sxs-lookup"><span data-stu-id="dfeae-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for View (Format) CustomItem Element for CustomEntry for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="dfeae-106">語法</span><span class="sxs-lookup"><span data-stu-id="dfeae-106">Syntax</span></span>

```xml
<CustomItem>
  <ExpressionBinding>...</ExpressionBinding>
  <Frame>...</Frame>
  <NewLine/>
  <Text>TextToDisplay</Text>
</CustomItem>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="dfeae-107">屬性與元素</span><span class="sxs-lookup"><span data-stu-id="dfeae-107">Attributes and Elements</span></span>

<span data-ttu-id="dfeae-108">下列各節說明屬性、 子項目和父項目`CustomItem`項目。</span><span class="sxs-lookup"><span data-stu-id="dfeae-108">The following sections describe attributes, child elements, and the parent element of the `CustomItem` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="dfeae-109">屬性</span><span class="sxs-lookup"><span data-stu-id="dfeae-109">Attributes</span></span>

<span data-ttu-id="dfeae-110">無。</span><span class="sxs-lookup"><span data-stu-id="dfeae-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="dfeae-111">子元素</span><span class="sxs-lookup"><span data-stu-id="dfeae-111">Child Elements</span></span>

|<span data-ttu-id="dfeae-112">元素</span><span class="sxs-lookup"><span data-stu-id="dfeae-112">Element</span></span>|<span data-ttu-id="dfeae-113">描述</span><span class="sxs-lookup"><span data-stu-id="dfeae-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="dfeae-114">ExpressionBinding CustomItem 如 CustomControl 檢視 （格式） 的項目</span><span class="sxs-lookup"><span data-stu-id="dfeae-114">ExpressionBinding Element for CustomItem for CustomControl for View (Format)</span></span>](./expressionbinding-element-for-customitem-for-customcontrol-for-view-format.md)|<span data-ttu-id="dfeae-115">選擇性的項目。</span><span class="sxs-lookup"><span data-stu-id="dfeae-115">Optional element.</span></span><br /><br /> <span data-ttu-id="dfeae-116">定義控制項所顯示的資料。</span><span class="sxs-lookup"><span data-stu-id="dfeae-116">Defines the data that is displayed by the control.</span></span>|
|[<span data-ttu-id="dfeae-117">CustomControl 檢視 （格式） 的 CustomItem 的框架項目</span><span class="sxs-lookup"><span data-stu-id="dfeae-117">Frame Element for CustomItem for CustomControl for View (Format)</span></span>](./frame-element-for-customitem-for-customcontrol-for-view-format.md)|<span data-ttu-id="dfeae-118">選擇性的項目。</span><span class="sxs-lookup"><span data-stu-id="dfeae-118">Optional element.</span></span><br /><br /> <span data-ttu-id="dfeae-119">定義自訂的控制項檢視所顯示的資料和顯示方式。</span><span class="sxs-lookup"><span data-stu-id="dfeae-119">Defines what data is displayed by the custom control view and how it is displayed.</span></span>|
|[<span data-ttu-id="dfeae-120">CustomItem 檢視 （格式） 的自訂控制項的新行項目</span><span class="sxs-lookup"><span data-stu-id="dfeae-120">NewLine Element for CustomItem for Custom Control for View (Format)</span></span>](./newline-element-for-customitem-for-customcontrol-for-view-format.md)|<span data-ttu-id="dfeae-121">選擇性的項目。</span><span class="sxs-lookup"><span data-stu-id="dfeae-121">Optional element.</span></span><br /><br /> <span data-ttu-id="dfeae-122">將控制項的顯示中的空白行。</span><span class="sxs-lookup"><span data-stu-id="dfeae-122">Adds a blank line to the display of the control.</span></span>|
|[<span data-ttu-id="dfeae-123">CustomItem CustomControl 檢視 （格式） 的文字項目</span><span class="sxs-lookup"><span data-stu-id="dfeae-123">Text Element for CustomItem for CustomControl for View (Format)</span></span>](./text-element-for-customitem-for-customview-for-view-format.md)|<span data-ttu-id="dfeae-124">選擇性的項目。</span><span class="sxs-lookup"><span data-stu-id="dfeae-124">Optional element.</span></span><br /><br /> <span data-ttu-id="dfeae-125">指定要由控制項所顯示的資料的其他文字。</span><span class="sxs-lookup"><span data-stu-id="dfeae-125">Specifies additional text to the data displayed by the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="dfeae-126">父元素</span><span class="sxs-lookup"><span data-stu-id="dfeae-126">Parent Elements</span></span>

|<span data-ttu-id="dfeae-127">元素</span><span class="sxs-lookup"><span data-stu-id="dfeae-127">Element</span></span>|<span data-ttu-id="dfeae-128">描述</span><span class="sxs-lookup"><span data-stu-id="dfeae-128">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="dfeae-129">CustomControl 檢視 （格式） 的 CustomEntries CustomEntry 項目</span><span class="sxs-lookup"><span data-stu-id="dfeae-129">CustomEntry Element for CustomEntries for CustomControl for View (Format)</span></span>](./customentry-element-for-customentries-for-customcontrol-for-view-format.md)|<span data-ttu-id="dfeae-130">提供自訂的控制項檢視的定義。</span><span class="sxs-lookup"><span data-stu-id="dfeae-130">Provides a definition of the custom control view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="dfeae-131">備註</span><span class="sxs-lookup"><span data-stu-id="dfeae-131">Remarks</span></span>

## <a name="see-also"></a><span data-ttu-id="dfeae-132">另請參閱</span><span class="sxs-lookup"><span data-stu-id="dfeae-132">See Also</span></span>

[<span data-ttu-id="dfeae-133">CustomEntry CustomEntries 檢視 （格式） 的項目</span><span class="sxs-lookup"><span data-stu-id="dfeae-133">CustomEntry Element for CustomEntries for View (Format)</span></span>](./customentry-element-for-customentries-for-customcontrol-for-view-format.md)

[<span data-ttu-id="dfeae-134">ExpressionBinding CustomItem 如 CustomControl 檢視 （格式） 的項目</span><span class="sxs-lookup"><span data-stu-id="dfeae-134">ExpressionBinding Element for CustomItem for CustomControl for View (Format)</span></span>](./expressionbinding-element-for-customitem-for-customcontrol-for-view-format.md)

[<span data-ttu-id="dfeae-135">CustomControl 檢視 （格式） 的 CustomItem 的框架項目</span><span class="sxs-lookup"><span data-stu-id="dfeae-135">Frame Element for CustomItem for CustomControl for View (Format)</span></span>](./frame-element-for-customitem-for-customcontrol-for-view-format.md)

[<span data-ttu-id="dfeae-136">CustomItem CustomControl 檢視 （格式） 的新行項目</span><span class="sxs-lookup"><span data-stu-id="dfeae-136">NewLine Element for CustomItem for CustomControl for View (Format)</span></span>](./newline-element-for-customitem-for-customcontrol-for-view-format.md)

[<span data-ttu-id="dfeae-137">CustomItem CustomControl 檢視 （格式） 的文字項目</span><span class="sxs-lookup"><span data-stu-id="dfeae-137">Text Element for CustomItem for CustomControl for View (Format)</span></span>](./text-element-for-customitem-for-customview-for-view-format.md)

[<span data-ttu-id="dfeae-138">撰寫 PowerShell 格式化檔案</span><span class="sxs-lookup"><span data-stu-id="dfeae-138">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)