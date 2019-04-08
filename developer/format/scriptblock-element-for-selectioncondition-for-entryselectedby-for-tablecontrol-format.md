---
title: TableControl （格式） 的 EntrySelectedBy 的 SelectionCondition 的指令碼區塊項目 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2b11fbcf-3426-48ae-9319-2c847969f723
caps.latest.revision: 10
ms.openlocfilehash: 7afc834e68ef332bee1e23da782fb5c5527fcf54
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/03/2019
ms.locfileid: "56855574"
---
# <a name="scriptblock-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format"></a><span data-ttu-id="f7231-102">TableControl 之 EntrySelectedBy 的 SelectionCondition 的 ScriptBlock 元素 (格式)</span><span class="sxs-lookup"><span data-stu-id="f7231-102">ScriptBlock Element for SelectionCondition for EntrySelectedBy for TableControl (Format)</span></span>

<span data-ttu-id="f7231-103">指定觸發條件的指令碼區塊。</span><span class="sxs-lookup"><span data-stu-id="f7231-103">Specifies the script block that triggers the condition.</span></span> <span data-ttu-id="f7231-104">此指令碼會評估為`true`、 符合條件，並使用資料表項目。</span><span class="sxs-lookup"><span data-stu-id="f7231-104">When this script is evaluated to `true`, the condition is met, and the table entry is used.</span></span>

<span data-ttu-id="f7231-105">組態項目 （格式） ViewDefinitions 項目 （格式） 檢視項目 （格式） TableControl 項目 （格式） TableRowEntries 項目 （格式） TableRowEntry 項目 （格式） EntrySelectedBy 項目 TableRowEntry （格式）SelectionCondition EntrySelectedBy TableRowEntry （格式） 的 EntrySelectedBy 的 SelectionCondition TableRowEntry （格式） ScriptBlock 元素的項目</span><span class="sxs-lookup"><span data-stu-id="f7231-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element (Format) TableRowEntry Element (Format) EntrySelectedBy Element for TableRowEntry (Format) SelectionCondition Element for EntrySelectedBy for TableRowEntry (Format) ScriptBlock Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="f7231-106">語法</span><span class="sxs-lookup"><span data-stu-id="f7231-106">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="f7231-107">屬性與元素</span><span class="sxs-lookup"><span data-stu-id="f7231-107">Attributes and Elements</span></span>

<span data-ttu-id="f7231-108">下列各節說明屬性、 子項目和父項目`ScriptBlock`項目。</span><span class="sxs-lookup"><span data-stu-id="f7231-108">The following sections describe attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="f7231-109">屬性</span><span class="sxs-lookup"><span data-stu-id="f7231-109">Attributes</span></span>

<span data-ttu-id="f7231-110">無。</span><span class="sxs-lookup"><span data-stu-id="f7231-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="f7231-111">子元素</span><span class="sxs-lookup"><span data-stu-id="f7231-111">Child Elements</span></span>

<span data-ttu-id="f7231-112">無。</span><span class="sxs-lookup"><span data-stu-id="f7231-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="f7231-113">父元素</span><span class="sxs-lookup"><span data-stu-id="f7231-113">Parent Elements</span></span>

|<span data-ttu-id="f7231-114">元素</span><span class="sxs-lookup"><span data-stu-id="f7231-114">Element</span></span>|<span data-ttu-id="f7231-115">描述</span><span class="sxs-lookup"><span data-stu-id="f7231-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="f7231-116">TableRowEntry （格式） 的 EntrySelectedBy SelectionCondition 項目</span><span class="sxs-lookup"><span data-stu-id="f7231-116">SelectionCondition Element for EntrySelectedBy for TableRowEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)|<span data-ttu-id="f7231-117">定義要使用此資料表項目必須存在的條件。</span><span class="sxs-lookup"><span data-stu-id="f7231-117">Defines the condition that must exist for this table entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="f7231-118">文字值</span><span class="sxs-lookup"><span data-stu-id="f7231-118">Text Value</span></span>

<span data-ttu-id="f7231-119">指定評估指令碼。</span><span class="sxs-lookup"><span data-stu-id="f7231-119">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="f7231-120">備註</span><span class="sxs-lookup"><span data-stu-id="f7231-120">Remarks</span></span>

<span data-ttu-id="f7231-121">選取條件，必須指定至少一個指令碼區塊或屬性名稱，但不能同時指定。</span><span class="sxs-lookup"><span data-stu-id="f7231-121">The selection condition must specify at least one script block or property name, but cannot specify both.</span></span> <span data-ttu-id="f7231-122">如需如何使用選擇條件的詳細資訊，請參閱[定義條件時檢視項目或項目用](./defining-conditions-for-displaying-data.md)。</span><span class="sxs-lookup"><span data-stu-id="f7231-122">For more information about how to use selection conditions, see [Defining Conditions for when a View Entry or Item is Used](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="f7231-123">資料表檢視元件的相關資訊，請參閱[建立資料表檢視](./creating-a-table-view.md)。</span><span class="sxs-lookup"><span data-stu-id="f7231-123">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="f7231-124">另請參閱</span><span class="sxs-lookup"><span data-stu-id="f7231-124">See Also</span></span>

[<span data-ttu-id="f7231-125">建立資料表檢視</span><span class="sxs-lookup"><span data-stu-id="f7231-125">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="f7231-126">定義何時顯示資料的條件</span><span class="sxs-lookup"><span data-stu-id="f7231-126">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="f7231-127">PropertyName TableRowEntry （格式） 的 EntrySelectedBy 的 SelectionCondition 的項目</span><span class="sxs-lookup"><span data-stu-id="f7231-127">PropertyName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>](./propertyname-element-for-selectioncondition-for-entryselectedby-for-tablerowentry-format.md)

[<span data-ttu-id="f7231-128">TableRowEntry （格式） 的 EntrySelectedBy SelectionCondition 項目</span><span class="sxs-lookup"><span data-stu-id="f7231-128">SelectionCondition Element for EntrySelectedBy for TableRowEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)

[<span data-ttu-id="f7231-129">撰寫 PowerShell 格式化檔案</span><span class="sxs-lookup"><span data-stu-id="f7231-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)