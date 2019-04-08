---
title: 用於檢視 （格式） 的控制項的畫面格 FirstLineIndent 項目 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ec63f4f9-8858-4529-8646-ffbbc278f83e
caps.latest.revision: 7
ms.openlocfilehash: 694c5baaa5e90a772257276ba139d90acf7ec0e3
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/03/2019
ms.locfileid: "56854314"
---
# <a name="firstlineindent-element-for-frame-for-controls-for-view-format"></a><span data-ttu-id="8f007-102">檢視之控制項的框架的 FirstLineIndent 元素 (格式)</span><span class="sxs-lookup"><span data-stu-id="8f007-102">FirstLineIndent Element for Frame for Controls for View (Format)</span></span>

<span data-ttu-id="8f007-103">指定資料的第一行向右移位的字元數。</span><span class="sxs-lookup"><span data-stu-id="8f007-103">Specifies how many characters the first line of data is shifted to the right.</span></span> <span data-ttu-id="8f007-104">定義可供檢視的控制項時，會使用這個項目。</span><span class="sxs-lookup"><span data-stu-id="8f007-104">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="8f007-105">組態項目 （格式） ViewDefinitions 項目 （格式） 檢視項目 （格式） 項目 （格式） 控制項的 Controls 項目控制項的檢視 （格式） CustomEntries 項目控制項的控制項的檢視 （格式） CustomControl 項目CustomControl CustomEntries CustomEntry CustomItem 檢視 （格式） 的畫面格的 FirstLineIndent 項目控制項的檢視 （格式） 框架元素的控制項的檢視 （格式） CustomItem 元素的控制項的檢視 （格式） CustomEntry 元素控制項的檢視 （格式） 的</span><span class="sxs-lookup"><span data-stu-id="8f007-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) CustomItem Element for CustomEntry for Controls for View (Format) Frame Element for CustomItem for Controls for View (Format) FirstLineIndent Element of Frame of Controls of View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="8f007-106">語法</span><span class="sxs-lookup"><span data-stu-id="8f007-106">Syntax</span></span>

```xml
<FirstLineIndent>NumberOfCharactersToShift</FirstLineIndent>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="8f007-107">屬性與元素</span><span class="sxs-lookup"><span data-stu-id="8f007-107">Attributes and Elements</span></span>

<span data-ttu-id="8f007-108">下列各節說明屬性、 子項目和父項目`FirstLineIndent`項目。</span><span class="sxs-lookup"><span data-stu-id="8f007-108">The following sections describe attributes, child elements, and parent element of the `FirstLineIndent` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="8f007-109">屬性</span><span class="sxs-lookup"><span data-stu-id="8f007-109">Attributes</span></span>

<span data-ttu-id="8f007-110">無。</span><span class="sxs-lookup"><span data-stu-id="8f007-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="8f007-111">子元素</span><span class="sxs-lookup"><span data-stu-id="8f007-111">Child Elements</span></span>

<span data-ttu-id="8f007-112">無。</span><span class="sxs-lookup"><span data-stu-id="8f007-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="8f007-113">父元素</span><span class="sxs-lookup"><span data-stu-id="8f007-113">Parent Elements</span></span>

|<span data-ttu-id="8f007-114">元素</span><span class="sxs-lookup"><span data-stu-id="8f007-114">Element</span></span>|<span data-ttu-id="8f007-115">描述</span><span class="sxs-lookup"><span data-stu-id="8f007-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="8f007-116">用於檢視 （格式） 的控制項 CustomItem 的框架項目</span><span class="sxs-lookup"><span data-stu-id="8f007-116">Frame Element for CustomItem for Controls for View (Format)</span></span>](./frame-element-for-customitem-for-controls-for-view-format.md)|<span data-ttu-id="8f007-117">定義資料的顯示方式，例如將資料轉移至左邊或右邊。</span><span class="sxs-lookup"><span data-stu-id="8f007-117">Defines how the data is displayed, such as shifting the data to the left or right.</span></span>|

## <a name="text-value"></a><span data-ttu-id="8f007-118">文字值</span><span class="sxs-lookup"><span data-stu-id="8f007-118">Text Value</span></span>

<span data-ttu-id="8f007-119">指定您想要移動資料的第一行的字元數。</span><span class="sxs-lookup"><span data-stu-id="8f007-119">Specify the number of characters that you want to shift the first line of the data.</span></span>

## <a name="remarks"></a><span data-ttu-id="8f007-120">備註</span><span class="sxs-lookup"><span data-stu-id="8f007-120">Remarks</span></span>

<span data-ttu-id="8f007-121">如果未指定這個項目，您無法指定[FirstLineHanging](./firstlinehanging-element-for-frame-for-controls-for-view-format.md)項目。</span><span class="sxs-lookup"><span data-stu-id="8f007-121">If this element is specified, you cannot specify the [FirstLineHanging](./firstlinehanging-element-for-frame-for-controls-for-view-format.md) element.</span></span>

## <a name="see-also"></a><span data-ttu-id="8f007-122">另請參閱</span><span class="sxs-lookup"><span data-stu-id="8f007-122">See Also</span></span>

[<span data-ttu-id="8f007-123">用於檢視 （格式） 的控制項的畫面格 FirstLineHanging 項目</span><span class="sxs-lookup"><span data-stu-id="8f007-123">FirstLineHanging Element for Frame for Controls for View (Format)</span></span>](./firstlinehanging-element-for-frame-for-controls-for-view-format.md)

[<span data-ttu-id="8f007-124">用於檢視 （格式） 的控制項 CustomItem 的框架項目</span><span class="sxs-lookup"><span data-stu-id="8f007-124">Frame Element for CustomItem for Controls for View (Format)</span></span>](./frame-element-for-customitem-for-controls-for-view-format.md)

[<span data-ttu-id="8f007-125">撰寫 PowerShell 格式化檔案</span><span class="sxs-lookup"><span data-stu-id="8f007-125">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)