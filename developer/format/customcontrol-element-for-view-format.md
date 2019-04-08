---
title: CustomControl 檢視 （格式） 的項目 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2edac16c-0b30-4985-ac84-0821aa9a9f6d
caps.latest.revision: 12
ms.openlocfilehash: bd0f7ca4de8dede97d1553cd62884ea45876e0c7
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/03/2019
ms.locfileid: "56861254"
---
# <a name="customcontrol-element-for-view-format"></a><span data-ttu-id="a27be-102">檢視的 CustomControl 元素 (格式)</span><span class="sxs-lookup"><span data-stu-id="a27be-102">CustomControl Element for View (Format)</span></span>

<span data-ttu-id="a27be-103">定義檢視的自訂控制項格式。</span><span class="sxs-lookup"><span data-stu-id="a27be-103">Defines a custom control format for the view.</span></span>

<span data-ttu-id="a27be-104">組態項目 （格式） ViewDefinitions 項目 （格式） 檢視項目 （格式） CustomControl 項目 （格式）</span><span class="sxs-lookup"><span data-stu-id="a27be-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="a27be-105">語法</span><span class="sxs-lookup"><span data-stu-id="a27be-105">Syntax</span></span>

```xml
<CustomControl>
  <CustomEntries>...</CustomEntries>
</CustomControl>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="a27be-106">屬性與元素</span><span class="sxs-lookup"><span data-stu-id="a27be-106">Attributes and Elements</span></span>

<span data-ttu-id="a27be-107">下列各節說明屬性、 子項目和父項目`CustomControl`項目。</span><span class="sxs-lookup"><span data-stu-id="a27be-107">The following sections describe attributes, child elements, and the parent element of the `CustomControl` element.</span></span> <span data-ttu-id="a27be-108">您必須指定一個子項目。</span><span class="sxs-lookup"><span data-stu-id="a27be-108">You must specify one child element.</span></span>

### <a name="attributes"></a><span data-ttu-id="a27be-109">屬性</span><span class="sxs-lookup"><span data-stu-id="a27be-109">Attributes</span></span>

<span data-ttu-id="a27be-110">無。</span><span class="sxs-lookup"><span data-stu-id="a27be-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="a27be-111">子元素</span><span class="sxs-lookup"><span data-stu-id="a27be-111">Child Elements</span></span>

|<span data-ttu-id="a27be-112">元素</span><span class="sxs-lookup"><span data-stu-id="a27be-112">Element</span></span>|<span data-ttu-id="a27be-113">描述</span><span class="sxs-lookup"><span data-stu-id="a27be-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="a27be-114">CustomEntries CustomControl 檢視 （格式） 的項目</span><span class="sxs-lookup"><span data-stu-id="a27be-114">CustomEntries Element for CustomControl for View (Format)</span></span>](./customentries-element-for-customcontrol-for-view-format.md)|<span data-ttu-id="a27be-115">必要項目。</span><span class="sxs-lookup"><span data-stu-id="a27be-115">Required element.</span></span><br /><br /> <span data-ttu-id="a27be-116">提供自訂的控制項檢視的定義。</span><span class="sxs-lookup"><span data-stu-id="a27be-116">Provides the definitions of the custom control view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="a27be-117">父元素</span><span class="sxs-lookup"><span data-stu-id="a27be-117">Parent Elements</span></span>

|<span data-ttu-id="a27be-118">元素</span><span class="sxs-lookup"><span data-stu-id="a27be-118">Element</span></span>|<span data-ttu-id="a27be-119">描述</span><span class="sxs-lookup"><span data-stu-id="a27be-119">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="a27be-120">檢視項目 （格式）</span><span class="sxs-lookup"><span data-stu-id="a27be-120">View Element (Format)</span></span>](./view-element-format.md)|<span data-ttu-id="a27be-121">定義用來顯示一或多個.NET 物件的檢視。</span><span class="sxs-lookup"><span data-stu-id="a27be-121">Defines a view that is used to display one or more .NET objects.</span></span>|

## <a name="remarks"></a><span data-ttu-id="a27be-122">備註</span><span class="sxs-lookup"><span data-stu-id="a27be-122">Remarks</span></span>

<span data-ttu-id="a27be-123">在大部分情況下，只有一個定義需要為每個控制項檢視中，但可提供多個定義，如果您想要使用相同的檢視來顯示不同的.NET 物件。</span><span class="sxs-lookup"><span data-stu-id="a27be-123">In most cases, only one definition is required for each control view, but it is possible to provide multiple definitions if you want to use the same view to display different .NET objects.</span></span> <span data-ttu-id="a27be-124">在這些情況下，您可以針對每個物件或一組物件提供不同的定義。</span><span class="sxs-lookup"><span data-stu-id="a27be-124">In those cases, you can provide a separate definition for each object or set of objects.</span></span>

## <a name="see-also"></a><span data-ttu-id="a27be-125">另請參閱</span><span class="sxs-lookup"><span data-stu-id="a27be-125">See Also</span></span>

[<span data-ttu-id="a27be-126">CustomEntries CustomControl 檢視 （格式） 的項目</span><span class="sxs-lookup"><span data-stu-id="a27be-126">CustomEntries Element for CustomControl for View (Format)</span></span>](./customentries-element-for-customcontrol-for-view-format.md)

[<span data-ttu-id="a27be-127">檢視項目 （格式）</span><span class="sxs-lookup"><span data-stu-id="a27be-127">View Element (Format)</span></span>](./view-element-format.md)

[<span data-ttu-id="a27be-128">撰寫 PowerShell 格式化檔案</span><span class="sxs-lookup"><span data-stu-id="a27be-128">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)