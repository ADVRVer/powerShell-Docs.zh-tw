---
title: PropertyName ListControl （格式） 的 EntrySelectedBy 的 SelectionCondition 的項目 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 71c3f1f6-6fe2-42f1-8260-6974d3871748
caps.latest.revision: 11
ms.openlocfilehash: 7d526372cf80327b3fb9b79b6e83429c57780183
ms.sourcegitcommit: caac7d098a448232304c9d6728e7340ec7517a71
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/16/2019
ms.locfileid: "58059009"
---
# <a name="propertyname-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format"></a><span data-ttu-id="b6a35-102">ListControl 之 EntrySelectedBy 的 SelectionCondition 的 PropertyName 元素 (格式)</span><span class="sxs-lookup"><span data-stu-id="b6a35-102">PropertyName Element for SelectionCondition for EntrySelectedBy for ListControl (Format)</span></span>

<span data-ttu-id="b6a35-103">指定觸發條件的.NET 屬性。</span><span class="sxs-lookup"><span data-stu-id="b6a35-103">Specifies the .NET property that triggers the condition.</span></span> <span data-ttu-id="b6a35-104">當這個屬性是存在，或當其評估結果為`true`、 符合條件，和使用清單項目。</span><span class="sxs-lookup"><span data-stu-id="b6a35-104">When this property is present or when it evaluates to `true`, the condition is met, and the list entry is used.</span></span>

<span data-ttu-id="b6a35-105">組態項目 （格式） ViewDefinitions 項目 （格式） 檢視項目 （格式） ListControl 項目 （格式） ListEntries 項目 （格式） ListEntry 項目 （格式） EntrySelectedBy 項目用於 ListEntry （格式） SelectionCondition 元素EntrySelectedBy ListEntry （格式） 的 EntrySelectedBy 的 SelectionCondition ListEntry （格式） PropertyName 元素</span><span class="sxs-lookup"><span data-stu-id="b6a35-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element (Format) ListEntry Element (Format) EntrySelectedBy Element for ListEntry (Format) SelectionCondition Element for EntrySelectedBy for ListEntry (Format) PropertyName Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="b6a35-106">語法</span><span class="sxs-lookup"><span data-stu-id="b6a35-106">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="b6a35-107">屬性與元素</span><span class="sxs-lookup"><span data-stu-id="b6a35-107">Attributes and Elements</span></span>

<span data-ttu-id="b6a35-108">下列各節說明屬性、 子項目和父項目`PropertyName`項目。</span><span class="sxs-lookup"><span data-stu-id="b6a35-108">The following sections describe attributes, child elements, and the parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="b6a35-109">屬性</span><span class="sxs-lookup"><span data-stu-id="b6a35-109">Attributes</span></span>

<span data-ttu-id="b6a35-110">無。</span><span class="sxs-lookup"><span data-stu-id="b6a35-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="b6a35-111">子元素</span><span class="sxs-lookup"><span data-stu-id="b6a35-111">Child Elements</span></span>

<span data-ttu-id="b6a35-112">無。</span><span class="sxs-lookup"><span data-stu-id="b6a35-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="b6a35-113">父元素</span><span class="sxs-lookup"><span data-stu-id="b6a35-113">Parent Elements</span></span>

|<span data-ttu-id="b6a35-114">元素</span><span class="sxs-lookup"><span data-stu-id="b6a35-114">Element</span></span>|<span data-ttu-id="b6a35-115">描述</span><span class="sxs-lookup"><span data-stu-id="b6a35-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="b6a35-116">ListEntry （格式） 的 EntrySelectedBy SelectionCondition 項目</span><span class="sxs-lookup"><span data-stu-id="b6a35-116">SelectionCondition Element for EntrySelectedBy for ListEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)|<span data-ttu-id="b6a35-117">定義要使用此清單項目必須存在的條件。</span><span class="sxs-lookup"><span data-stu-id="b6a35-117">Defines the condition that must exist for this list entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="b6a35-118">文字值</span><span class="sxs-lookup"><span data-stu-id="b6a35-118">Text Value</span></span>

<span data-ttu-id="b6a35-119">指定.NET 屬性名稱。</span><span class="sxs-lookup"><span data-stu-id="b6a35-119">Specify the .NET property name.</span></span>

## <a name="remarks"></a><span data-ttu-id="b6a35-120">備註</span><span class="sxs-lookup"><span data-stu-id="b6a35-120">Remarks</span></span>

<span data-ttu-id="b6a35-121">選取條件必須指定至少一個屬性名稱或指令碼區塊，但不能同時指定。</span><span class="sxs-lookup"><span data-stu-id="b6a35-121">The selection condition must specify at least one property name or a script block, but cannot specify both.</span></span> <span data-ttu-id="b6a35-122">如需如何使用選擇條件的詳細資訊，請參閱[定義條件時檢視項目或項目用](./defining-conditions-for-displaying-data.md)。</span><span class="sxs-lookup"><span data-stu-id="b6a35-122">For more information about how to use selection conditions, see [Defining Conditions for when a View Entry or Item is Used](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="b6a35-123">清單檢視的其他元件的相關資訊，請參閱[建立清單檢視](./creating-a-list-view.md)。</span><span class="sxs-lookup"><span data-stu-id="b6a35-123">For more information about other components of a list view, see [Creating List View](./creating-a-list-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="b6a35-124">另請參閱</span><span class="sxs-lookup"><span data-stu-id="b6a35-124">See Also</span></span>

[<span data-ttu-id="b6a35-125">建立清單檢視</span><span class="sxs-lookup"><span data-stu-id="b6a35-125">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="b6a35-126">定義條件的資料時顯示</span><span class="sxs-lookup"><span data-stu-id="b6a35-126">Defining Conditions for When Data is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="b6a35-127">ListEntry 項目 （格式）</span><span class="sxs-lookup"><span data-stu-id="b6a35-127">ListEntry Element (Format)</span></span>](./listentry-element-for-listcontrol-format.md)

[<span data-ttu-id="b6a35-128">針對 ListEntry （格式） 的 EntrySelectedBy SelectionCondition 的指令碼區塊項目</span><span class="sxs-lookup"><span data-stu-id="b6a35-128">ScriptBlock Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format.md)

[<span data-ttu-id="b6a35-129">撰寫 PowerShell 格式化檔案</span><span class="sxs-lookup"><span data-stu-id="b6a35-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)