---
title: TableControl （格式） 的 TableColumnItem 對齊項目 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b07a53df-64f1-49b0-8cea-c993b3f1f76b
caps.latest.revision: 10
ms.openlocfilehash: 1bc936b94ee6fd6239e9e3c4afcdb8f14fbe36eb
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/03/2019
ms.locfileid: "56858204"
---
# <a name="alignment-element-for-tablecolumnitem-for-tablecontrol-format"></a><span data-ttu-id="220ba-102">TableControl 之 TableColumnItem 的對齊元素 (格式)</span><span class="sxs-lookup"><span data-stu-id="220ba-102">Alignment Element for TableColumnItem for TableControl (Format)</span></span>

<span data-ttu-id="220ba-103">定義資料列的資料行中資料的顯示方式。</span><span class="sxs-lookup"><span data-stu-id="220ba-103">Defines how the data in a column of the row is displayed.</span></span>

<span data-ttu-id="220ba-104">組態項目 （格式） ViewDefinitions 項目 （格式） 檢視項目 （格式） TableControl 項目 （格式） TableRowEntries 項目 （格式） TableRowEntry 項目 （格式） TableColumnItems 項目 （格式） TableColumnItem 項目 （格式）TableColumnItem （格式） 的對齊項目</span><span class="sxs-lookup"><span data-stu-id="220ba-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element (Format) TableRowEntry Element (Format) TableColumnItems Element (Format) TableColumnItem Element (Format) Alignment Element for TableColumnItem (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="220ba-105">語法</span><span class="sxs-lookup"><span data-stu-id="220ba-105">Syntax</span></span>

```xml
<Alignment>AlignmentType</Alignment>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="220ba-106">屬性與元素</span><span class="sxs-lookup"><span data-stu-id="220ba-106">Attributes and Elements</span></span>

<span data-ttu-id="220ba-107">下列各節說明屬性、 子項目和父項目`Alignment`項目。</span><span class="sxs-lookup"><span data-stu-id="220ba-107">The following sections describe the attributes, child elements, and parent element of the `Alignment` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="220ba-108">屬性</span><span class="sxs-lookup"><span data-stu-id="220ba-108">Attributes</span></span>

<span data-ttu-id="220ba-109">無。</span><span class="sxs-lookup"><span data-stu-id="220ba-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="220ba-110">子元素</span><span class="sxs-lookup"><span data-stu-id="220ba-110">Child Elements</span></span>

<span data-ttu-id="220ba-111">無。</span><span class="sxs-lookup"><span data-stu-id="220ba-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="220ba-112">父元素</span><span class="sxs-lookup"><span data-stu-id="220ba-112">Parent Elements</span></span>

|<span data-ttu-id="220ba-113">元素</span><span class="sxs-lookup"><span data-stu-id="220ba-113">Element</span></span>|<span data-ttu-id="220ba-114">描述</span><span class="sxs-lookup"><span data-stu-id="220ba-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="220ba-115">TableColumnItem 項目 （格式）</span><span class="sxs-lookup"><span data-stu-id="220ba-115">TableColumnItem Element (Format)</span></span>](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md)|<span data-ttu-id="220ba-116">定義標籤、 寬度和資料行的資料表資料的對齊方式。</span><span class="sxs-lookup"><span data-stu-id="220ba-116">Defines a label, the width, and the alignment of the data for a column of the table.</span></span>|

## <a name="text-value"></a><span data-ttu-id="220ba-117">文字值</span><span class="sxs-lookup"><span data-stu-id="220ba-117">Text Value</span></span>

<span data-ttu-id="220ba-118">指定下列值之一。</span><span class="sxs-lookup"><span data-stu-id="220ba-118">Specify one of the following values.</span></span> <span data-ttu-id="220ba-119">（這些值都不區分大小寫）。</span><span class="sxs-lookup"><span data-stu-id="220ba-119">(These values are not case-sensitive.)</span></span>

<span data-ttu-id="220ba-120">左的移位左邊資料行中顯示的資料。</span><span class="sxs-lookup"><span data-stu-id="220ba-120">Left Shifts the data displayed in the column to the left.</span></span> <span data-ttu-id="220ba-121">（這是預設值如果不指定這個元素。）</span><span class="sxs-lookup"><span data-stu-id="220ba-121">(This is the default if this element is not specified.)</span></span>

<span data-ttu-id="220ba-122">右移位右側資料行中顯示的資料。</span><span class="sxs-lookup"><span data-stu-id="220ba-122">Right Shifts the data displayed in the column to the right.</span></span>

<span data-ttu-id="220ba-123">Center 中心資料行中顯示的資料。</span><span class="sxs-lookup"><span data-stu-id="220ba-123">Center Centers the data displayed in the column.</span></span>

## <a name="remarks"></a><span data-ttu-id="220ba-124">備註</span><span class="sxs-lookup"><span data-stu-id="220ba-124">Remarks</span></span>

<span data-ttu-id="220ba-125">資料表檢視元件的相關資訊，請參閱[資料表檢視](./creating-a-table-view.md)。</span><span class="sxs-lookup"><span data-stu-id="220ba-125">For more information about the components of a table view, see [Table View](./creating-a-table-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="220ba-126">另請參閱</span><span class="sxs-lookup"><span data-stu-id="220ba-126">See Also</span></span>

[<span data-ttu-id="220ba-127">資料表檢視</span><span class="sxs-lookup"><span data-stu-id="220ba-127">Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="220ba-128">TableColumnItem 項目 （格式）</span><span class="sxs-lookup"><span data-stu-id="220ba-128">TableColumnItem Element (Format)</span></span>](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md)