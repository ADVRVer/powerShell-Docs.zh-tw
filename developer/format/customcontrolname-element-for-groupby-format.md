---
title: CustomControlName GroupBy （格式） 的項目 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 473d9b56-521b-479a-8010-67fe9f040063
caps.latest.revision: 8
ms.openlocfilehash: 3a386eff95044eae573c255a451c5c8b8f16714d
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/03/2019
ms.locfileid: "56860304"
---
# <a name="customcontrolname-element-for-groupby-format"></a><span data-ttu-id="eea88-102">GroupBy 的 CustomControlName 元素 (格式)</span><span class="sxs-lookup"><span data-stu-id="eea88-102">CustomControlName Element for GroupBy (Format)</span></span>

<span data-ttu-id="eea88-103">指定用來顯示新的群組的自訂控制項的名稱。</span><span class="sxs-lookup"><span data-stu-id="eea88-103">Specifies the name of a custom control that is used to display the new group.</span></span> <span data-ttu-id="eea88-104">定義資料表、 清單、 寬或自訂的控制項檢視時，會使用這個項目。</span><span class="sxs-lookup"><span data-stu-id="eea88-104">This element is used when defining a table, list, wide or custom control view.</span></span>

<span data-ttu-id="eea88-105">組態項目 （格式） ViewDefinitions 項目 （格式） 檢視項目 （格式） GroupBy 項目檢視 （格式） 的 GroupBy （格式） 的 CustomControlName 項目</span><span class="sxs-lookup"><span data-stu-id="eea88-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControlName Element of GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="eea88-106">語法</span><span class="sxs-lookup"><span data-stu-id="eea88-106">Syntax</span></span>

```xml
<CustomControlName>ControlName</CustomControlName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="eea88-107">屬性與元素</span><span class="sxs-lookup"><span data-stu-id="eea88-107">Attributes and Elements</span></span>

<span data-ttu-id="eea88-108">下列各節說明屬性、 子項目和父項目`CustomControlName`項目。</span><span class="sxs-lookup"><span data-stu-id="eea88-108">The following sections describe the attributes, child elements, and parent elements of the `CustomControlName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="eea88-109">屬性</span><span class="sxs-lookup"><span data-stu-id="eea88-109">Attributes</span></span>

<span data-ttu-id="eea88-110">無。</span><span class="sxs-lookup"><span data-stu-id="eea88-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="eea88-111">子元素</span><span class="sxs-lookup"><span data-stu-id="eea88-111">Child Elements</span></span>

<span data-ttu-id="eea88-112">無。</span><span class="sxs-lookup"><span data-stu-id="eea88-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="eea88-113">父元素</span><span class="sxs-lookup"><span data-stu-id="eea88-113">Parent Elements</span></span>

|<span data-ttu-id="eea88-114">元素</span><span class="sxs-lookup"><span data-stu-id="eea88-114">Element</span></span>|<span data-ttu-id="eea88-115">描述</span><span class="sxs-lookup"><span data-stu-id="eea88-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="eea88-116">檢視 （格式） 的 GroupBy 元素</span><span class="sxs-lookup"><span data-stu-id="eea88-116">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)|<span data-ttu-id="eea88-117">定義 Windows PowerShell 顯示新的一整組物件的方式。</span><span class="sxs-lookup"><span data-stu-id="eea88-117">Defines how Windows PowerShell displays a new group of objects.</span></span>|

## <a name="text-value"></a><span data-ttu-id="eea88-118">文字值</span><span class="sxs-lookup"><span data-stu-id="eea88-118">Text Value</span></span>

<span data-ttu-id="eea88-119">指定自訂控制項是用來顯示新的群組名稱。</span><span class="sxs-lookup"><span data-stu-id="eea88-119">Specify the name of the custom control that is used to display a new group.</span></span>

## <a name="remarks"></a><span data-ttu-id="eea88-120">備註</span><span class="sxs-lookup"><span data-stu-id="eea88-120">Remarks</span></span>

<span data-ttu-id="eea88-121">您可以建立可供所有的格式化檔案，檢視的通用控制項，而且您可以建立可供特定檢視的檢視控制項。</span><span class="sxs-lookup"><span data-stu-id="eea88-121">You can create common controls that can be used by all the views of a formatting file, and you can create view controls that can be used by a specific view.</span></span> <span data-ttu-id="eea88-122">下列項目會指定這些自訂控制項的名稱：</span><span class="sxs-lookup"><span data-stu-id="eea88-122">The following elements specify the names of these custom controls:</span></span>

- [<span data-ttu-id="eea88-123">組態 （格式） 的控制項的控制項的 name 元素</span><span class="sxs-lookup"><span data-stu-id="eea88-123">Name Element for Control for Controls for Configuration (Format)</span></span>](./name-element-for-control-for-controls-for-configuration-format.md)

- [<span data-ttu-id="eea88-124">用於檢視 （格式） 的控制項的控制項的 name 元素</span><span class="sxs-lookup"><span data-stu-id="eea88-124">Name Element for Control for Controls for View (Format)</span></span>](./name-element-for-control-for-controls-for-view-format.md)

## <a name="see-also"></a><span data-ttu-id="eea88-125">另請參閱</span><span class="sxs-lookup"><span data-stu-id="eea88-125">See Also</span></span>

[<span data-ttu-id="eea88-126">檢視 （格式） 的 GroupBy 元素</span><span class="sxs-lookup"><span data-stu-id="eea88-126">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)

[<span data-ttu-id="eea88-127">組態 （格式） 的控制項的控制項的 name 元素</span><span class="sxs-lookup"><span data-stu-id="eea88-127">Name Element for Control for Controls for Configuration (Format)</span></span>](./name-element-for-control-for-controls-for-configuration-format.md)

[<span data-ttu-id="eea88-128">用於檢視 （格式） 的控制項的控制項的 name 元素</span><span class="sxs-lookup"><span data-stu-id="eea88-128">Name Element for Control for Controls for View (Format)</span></span>](./name-element-for-control-for-controls-for-view-format.md)

[<span data-ttu-id="eea88-129">撰寫 PowerShell 格式化檔案</span><span class="sxs-lookup"><span data-stu-id="eea88-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)