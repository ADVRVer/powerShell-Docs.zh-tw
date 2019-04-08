---
title: CustomControl GroupBy （格式） 的項目 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2472e256-8f4f-4288-8b67-a3300649dafa
caps.latest.revision: 9
ms.openlocfilehash: 2e84e770a345e272d4c5917b00afe7520840e1db
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/03/2019
ms.locfileid: "56853744"
---
# <a name="customcontrol-element-for-groupby-format"></a><span data-ttu-id="47459-102">GroupBy 的 CustomControl 元素 (格式)</span><span class="sxs-lookup"><span data-stu-id="47459-102">CustomControl Element for GroupBy (Format)</span></span>

<span data-ttu-id="47459-103">定義自訂控制項，則會顯示新的群組。</span><span class="sxs-lookup"><span data-stu-id="47459-103">Defines the custom control that displays the new group.</span></span>

<span data-ttu-id="47459-104">組態項目 （格式） ViewDefinitions 項目 （格式） 檢視項目 （格式） GroupBy 項目檢視 （格式） 的 GroupBy （格式） 的 CustomControl 項目</span><span class="sxs-lookup"><span data-stu-id="47459-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="47459-105">語法</span><span class="sxs-lookup"><span data-stu-id="47459-105">Syntax</span></span>

```xml
<CustomControl>
  <CustomEntries>...</CustomEntries>
<CustomControl>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="47459-106">屬性與元素</span><span class="sxs-lookup"><span data-stu-id="47459-106">Attributes and Elements</span></span>

<span data-ttu-id="47459-107">下列各節說明屬性、 子項目和父項目`CustomControl`項目。</span><span class="sxs-lookup"><span data-stu-id="47459-107">The following sections describe the attributes, child elements, and parent element of the `CustomControl` element.</span></span> <span data-ttu-id="47459-108">您可以指定任意數目的子項目，並以任何順序列出。</span><span class="sxs-lookup"><span data-stu-id="47459-108">You can specify any number of child elements and list them in any order.</span></span>

### <a name="attributes"></a><span data-ttu-id="47459-109">屬性</span><span class="sxs-lookup"><span data-stu-id="47459-109">Attributes</span></span>

<span data-ttu-id="47459-110">無。</span><span class="sxs-lookup"><span data-stu-id="47459-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="47459-111">子元素</span><span class="sxs-lookup"><span data-stu-id="47459-111">Child Elements</span></span>

|<span data-ttu-id="47459-112">元素</span><span class="sxs-lookup"><span data-stu-id="47459-112">Element</span></span>|<span data-ttu-id="47459-113">描述</span><span class="sxs-lookup"><span data-stu-id="47459-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="47459-114">GroupBy （格式） 的 CustomControl CustomEntries 項目</span><span class="sxs-lookup"><span data-stu-id="47459-114">CustomEntries Element for CustomControl for GroupBy (Format)</span></span>](./customentries-element-for-customcontrol-for-groupby-format.md)|<span data-ttu-id="47459-115">必要項目。</span><span class="sxs-lookup"><span data-stu-id="47459-115">Required element.</span></span><br /><br /> <span data-ttu-id="47459-116">提供控制項的定義。</span><span class="sxs-lookup"><span data-stu-id="47459-116">Provides the definitions for the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="47459-117">父元素</span><span class="sxs-lookup"><span data-stu-id="47459-117">Parent Elements</span></span>

|<span data-ttu-id="47459-118">元素</span><span class="sxs-lookup"><span data-stu-id="47459-118">Element</span></span>|<span data-ttu-id="47459-119">描述</span><span class="sxs-lookup"><span data-stu-id="47459-119">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="47459-120">檢視 （格式） 的 GroupBy 元素</span><span class="sxs-lookup"><span data-stu-id="47459-120">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)|<span data-ttu-id="47459-121">定義 Windows PowerShell 顯示新的一整組物件的方式。</span><span class="sxs-lookup"><span data-stu-id="47459-121">Defines how Windows PowerShell displays a new group of objects.</span></span>|

## <a name="remarks"></a><span data-ttu-id="47459-122">備註</span><span class="sxs-lookup"><span data-stu-id="47459-122">Remarks</span></span>

## <a name="see-also"></a><span data-ttu-id="47459-123">另請參閱</span><span class="sxs-lookup"><span data-stu-id="47459-123">See Also</span></span>

[<span data-ttu-id="47459-124">GroupBy （格式） 的 CustomControl CustomEntries 項目</span><span class="sxs-lookup"><span data-stu-id="47459-124">CustomEntries Element for CustomControl for GroupBy (Format)</span></span>](./customentries-element-for-customcontrol-for-groupby-format.md)

[<span data-ttu-id="47459-125">檢視 （格式） 的 GroupBy 元素</span><span class="sxs-lookup"><span data-stu-id="47459-125">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)

[<span data-ttu-id="47459-126">撰寫 PowerShell 格式化檔案</span><span class="sxs-lookup"><span data-stu-id="47459-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)