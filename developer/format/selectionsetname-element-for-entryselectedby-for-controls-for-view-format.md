---
title: 用於檢視 （格式） 的控制項 EntrySelectedBy SelectionSetName 項目 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b594a064-746f-4900-99e4-7be7bf5aa5a2
caps.latest.revision: 7
ms.openlocfilehash: d540c99707f4e0796b2d408f2161a9208257ab32
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/03/2019
ms.locfileid: "56860994"
---
# <a name="selectionsetname-element-for-entryselectedby-for-controls-for-view-format"></a><span data-ttu-id="a53dc-102">檢視之控制項的 EntrySelectedBy 的 SelectionSetName 元素 (格式)</span><span class="sxs-lookup"><span data-stu-id="a53dc-102">SelectionSetName Element for EntrySelectedBy for Controls for View (Format)</span></span>

<span data-ttu-id="a53dc-103">指定一組使用這個控制項定義的.NET 型別。</span><span class="sxs-lookup"><span data-stu-id="a53dc-103">Specifies a set of .NET types that use this definition of the control.</span></span> <span data-ttu-id="a53dc-104">定義可供檢視的控制項時，會使用這個項目。</span><span class="sxs-lookup"><span data-stu-id="a53dc-104">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="a53dc-105">組態項目 （格式） ViewDefinitions 項目 （格式） 檢視項目 （格式） 項目 （格式） 控制項的 Controls 項目控制項的檢視 （格式） CustomEntries 項目控制項的控制項的檢視 （格式） CustomControl 項目CustomControl CustomEntries CustomEntry EntrySelectedBy 的檢視 （控制項的檢視 （格式） SelectionSetName 元素的控制項的檢視 （格式） EntrySelectedBy 元素的控制項的檢視 （格式） CustomEntry 元素的控制項格式）</span><span class="sxs-lookup"><span data-stu-id="a53dc-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for Controls for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) EntrySelectedBy Element for CustomEntry for Controls for View (Format) SelectionSetName Element for EntrySelectedBy for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="a53dc-106">語法</span><span class="sxs-lookup"><span data-stu-id="a53dc-106">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="a53dc-107">屬性與元素</span><span class="sxs-lookup"><span data-stu-id="a53dc-107">Attributes and Elements</span></span>

<span data-ttu-id="a53dc-108">下列各節說明屬性、 子項目和父項目`SelectionSetName`項目。</span><span class="sxs-lookup"><span data-stu-id="a53dc-108">The following sections describe attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="a53dc-109">屬性</span><span class="sxs-lookup"><span data-stu-id="a53dc-109">Attributes</span></span>

<span data-ttu-id="a53dc-110">無</span><span class="sxs-lookup"><span data-stu-id="a53dc-110">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="a53dc-111">子元素</span><span class="sxs-lookup"><span data-stu-id="a53dc-111">Child Elements</span></span>

<span data-ttu-id="a53dc-112">無。</span><span class="sxs-lookup"><span data-stu-id="a53dc-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="a53dc-113">父元素</span><span class="sxs-lookup"><span data-stu-id="a53dc-113">Parent Elements</span></span>

|<span data-ttu-id="a53dc-114">元素</span><span class="sxs-lookup"><span data-stu-id="a53dc-114">Element</span></span>|<span data-ttu-id="a53dc-115">描述</span><span class="sxs-lookup"><span data-stu-id="a53dc-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="a53dc-116">用於檢視 （格式） 的控制項 CustomEntry EntrySelectedBy 項目</span><span class="sxs-lookup"><span data-stu-id="a53dc-116">EntrySelectedBy Element for CustomEntry for Controls for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-controls-for-view-format.md)|<span data-ttu-id="a53dc-117">定義使用此控制項定義或必須存在於要使用此定義條件的.NET 類型。</span><span class="sxs-lookup"><span data-stu-id="a53dc-117">Defines the .NET types that use this control definition or the condition that must exist for this definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="a53dc-118">文字值</span><span class="sxs-lookup"><span data-stu-id="a53dc-118">Text Value</span></span>

<span data-ttu-id="a53dc-119">指定選取項目集的名稱。</span><span class="sxs-lookup"><span data-stu-id="a53dc-119">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="a53dc-120">備註</span><span class="sxs-lookup"><span data-stu-id="a53dc-120">Remarks</span></span>

<span data-ttu-id="a53dc-121">每個控制項定義必須至少一個型別名稱、 選取項目集或選擇條件的定義。</span><span class="sxs-lookup"><span data-stu-id="a53dc-121">Each control definition must have at least one type name, selection set, or selection condition defined.</span></span>

<span data-ttu-id="a53dc-122">您想要在多個檢視中定義一組所使用的物件時，會通常會使用選取項目集。</span><span class="sxs-lookup"><span data-stu-id="a53dc-122">Selection sets are typically used when you want to define a group of objects that are used in multiple views.</span></span> <span data-ttu-id="a53dc-123">如需定義選取項目集的詳細資訊，請參閱[定義的選取項目設定](./defining-selection-sets.md)。</span><span class="sxs-lookup"><span data-stu-id="a53dc-123">For more information about defining selection sets, see [Defining Selection Sets](./defining-selection-sets.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="a53dc-124">另請參閱</span><span class="sxs-lookup"><span data-stu-id="a53dc-124">See Also</span></span>

[<span data-ttu-id="a53dc-125">用於檢視 （格式） 的控制項 CustomEntry EntrySelectedBy 項目</span><span class="sxs-lookup"><span data-stu-id="a53dc-125">EntrySelectedBy Element for CustomEntry for Controls for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-controls-for-view-format.md)

[<span data-ttu-id="a53dc-126">撰寫 PowerShell 格式化檔案</span><span class="sxs-lookup"><span data-stu-id="a53dc-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)