---
title: 用於檢視 （格式） 的控制項 CustomEntries CustomEntry 項目 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c6739205-2bc9-4507-b2af-d19d548c2057
caps.latest.revision: 6
ms.openlocfilehash: b92b99d88992cf13dbf7bfbe88aad603615f3138
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/03/2019
ms.locfileid: "56858774"
---
# <a name="customentry-element-for-customentries-for-controls-for-view-format"></a><span data-ttu-id="b63aa-102">檢視之控制項的 CustomEntries 的 CustomEntry 元素 (格式)</span><span class="sxs-lookup"><span data-stu-id="b63aa-102">CustomEntry Element for CustomEntries for Controls for View (Format)</span></span>

<span data-ttu-id="b63aa-103">提供控制項的定義。</span><span class="sxs-lookup"><span data-stu-id="b63aa-103">Provides a definition of the control.</span></span> <span data-ttu-id="b63aa-104">定義可供檢視的控制項時，會使用這個項目。</span><span class="sxs-lookup"><span data-stu-id="b63aa-104">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="b63aa-105">組態項目 （格式） ViewDefinitions 項目 （格式） 檢視項目 （格式） 項目 （格式） 控制項的 Controls 項目控制項的檢視 （格式） CustomEntries 項目控制項的控制項的檢視 （格式） CustomControl 項目CustomControl CustomEntries 用於檢視 （格式） 的控制項的檢視 （格式） CustomEntry 元素</span><span class="sxs-lookup"><span data-stu-id="b63aa-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="b63aa-106">語法</span><span class="sxs-lookup"><span data-stu-id="b63aa-106">Syntax</span></span>

```xml
<CustomEntry>
  <EntrySelectedBy>...</EntrySelectedBy>
  <CustomItem>...</CustomItem>
</CustomEntry>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="b63aa-107">屬性與元素</span><span class="sxs-lookup"><span data-stu-id="b63aa-107">Attributes and Elements</span></span>

<span data-ttu-id="b63aa-108">下列各節說明屬性、 子項目，以及的父項目`CustomEntry`項目。</span><span class="sxs-lookup"><span data-stu-id="b63aa-108">The following sections describe attributes, child elements, and the parent elements of the `CustomEntry` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="b63aa-109">屬性</span><span class="sxs-lookup"><span data-stu-id="b63aa-109">Attributes</span></span>

<span data-ttu-id="b63aa-110">無。</span><span class="sxs-lookup"><span data-stu-id="b63aa-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="b63aa-111">子元素</span><span class="sxs-lookup"><span data-stu-id="b63aa-111">Child Elements</span></span>

|<span data-ttu-id="b63aa-112">元素</span><span class="sxs-lookup"><span data-stu-id="b63aa-112">Element</span></span>|<span data-ttu-id="b63aa-113">描述</span><span class="sxs-lookup"><span data-stu-id="b63aa-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="b63aa-114">用於檢視 （格式） 的控制項 CustomEntry EntrySelectedBy 項目</span><span class="sxs-lookup"><span data-stu-id="b63aa-114">EntrySelectedBy Element for CustomEntry for Controls for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-controls-for-view-format.md)|<span data-ttu-id="b63aa-115">選擇性的項目。</span><span class="sxs-lookup"><span data-stu-id="b63aa-115">Optional element.</span></span><br /><br /> <span data-ttu-id="b63aa-116">定義使用此控制項定義或必須存在於要使用此定義條件的.NET 類型。</span><span class="sxs-lookup"><span data-stu-id="b63aa-116">Defines the .NET types that use this control definition or the condition that must exist for this definition to be used.</span></span>|
|[<span data-ttu-id="b63aa-117">用於檢視 （格式） 的控制項 CustomEntry CustomItem 項目</span><span class="sxs-lookup"><span data-stu-id="b63aa-117">CustomItem Element for CustomEntry for Controls for View (Format)</span></span>](./customitem-element-for-customentry-for-controls-for-view-format.md)|<span data-ttu-id="b63aa-118">必要項目。</span><span class="sxs-lookup"><span data-stu-id="b63aa-118">Required element.</span></span><br /><br /> <span data-ttu-id="b63aa-119">定義控制項顯示資料的方式。</span><span class="sxs-lookup"><span data-stu-id="b63aa-119">Defines how the control displays the data.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="b63aa-120">父元素</span><span class="sxs-lookup"><span data-stu-id="b63aa-120">Parent Elements</span></span>

|<span data-ttu-id="b63aa-121">元素</span><span class="sxs-lookup"><span data-stu-id="b63aa-121">Element</span></span>|<span data-ttu-id="b63aa-122">描述</span><span class="sxs-lookup"><span data-stu-id="b63aa-122">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="b63aa-123">CustomEntries CustomControl 檢視 （格式） 的項目</span><span class="sxs-lookup"><span data-stu-id="b63aa-123">CustomEntries Element for CustomControl for View (Format)</span></span>](./customentries-element-for-customcontrol-for-view-format.md)|<span data-ttu-id="b63aa-124">提供控制項的定義。</span><span class="sxs-lookup"><span data-stu-id="b63aa-124">Provides the definitions for the control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="b63aa-125">備註</span><span class="sxs-lookup"><span data-stu-id="b63aa-125">Remarks</span></span>

## <a name="see-also"></a><span data-ttu-id="b63aa-126">另請參閱</span><span class="sxs-lookup"><span data-stu-id="b63aa-126">See Also</span></span>

[<span data-ttu-id="b63aa-127">CustomEntries CustomControl 檢視 （格式） 的項目</span><span class="sxs-lookup"><span data-stu-id="b63aa-127">CustomEntries Element for CustomControl for View (Format)</span></span>](./customentries-element-for-customcontrol-for-view-format.md)

[<span data-ttu-id="b63aa-128">撰寫 PowerShell 格式化檔案</span><span class="sxs-lookup"><span data-stu-id="b63aa-128">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)