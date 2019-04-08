---
title: 數量參數 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8c0bd8a9-1749-4885-ab24-38c0a4d9f2cb
caps.latest.revision: 6
ms.openlocfilehash: 7a3efc60fcc8729d833f6de070016cfd08cc9b88
ms.sourcegitcommit: ce46e5098786e19d521b4bf948ff62d2b90bc53e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/02/2019
ms.locfileid: "57251365"
---
# <a name="quantity-parameters"></a><span data-ttu-id="67c1f-102">數量參數</span><span class="sxs-lookup"><span data-stu-id="67c1f-102">Quantity Parameters</span></span>

<span data-ttu-id="67c1f-103">下表列出建議的名稱和數量參數的功能。</span><span class="sxs-lookup"><span data-stu-id="67c1f-103">The following table lists the recommended names and functionality for quantity parameters.</span></span>

|<span data-ttu-id="67c1f-104">參數</span><span class="sxs-lookup"><span data-stu-id="67c1f-104">Parameter</span></span>|<span data-ttu-id="67c1f-105">功能</span><span class="sxs-lookup"><span data-stu-id="67c1f-105">Functionality</span></span>|
|---|---|
|<span data-ttu-id="67c1f-106">**所有**</span><span class="sxs-lookup"><span data-stu-id="67c1f-106">**All**</span></span><br><span data-ttu-id="67c1f-107">資料類型：布林值</span><span class="sxs-lookup"><span data-stu-id="67c1f-107">Data type: Boolean</span></span>|<span data-ttu-id="67c1f-108">實作此參數，讓`true`表示所有資源應該都作用時，而不是預設資源子集。</span><span class="sxs-lookup"><span data-stu-id="67c1f-108">Implement this parameter so that `true` indicates that all resources should be acted upon instead of a default subset of resources.</span></span> <span data-ttu-id="67c1f-109">實作此參數，讓`false`表示資源的子集。</span><span class="sxs-lookup"><span data-stu-id="67c1f-109">Implement this parameter so that `false` indicates a subset of the resources.</span></span>|
|<span data-ttu-id="67c1f-110">**配置**</span><span class="sxs-lookup"><span data-stu-id="67c1f-110">**Allocation**</span></span><br><span data-ttu-id="67c1f-111">資料類型：Int32</span><span class="sxs-lookup"><span data-stu-id="67c1f-111">Data type: Int32</span></span>|<span data-ttu-id="67c1f-112">實作此參數，讓使用者可以指定要配置的項目數。</span><span class="sxs-lookup"><span data-stu-id="67c1f-112">Implement this parameter so that the user can specify the number of items to allocate.</span></span>|
|<span data-ttu-id="67c1f-113">**BlockCount**</span><span class="sxs-lookup"><span data-stu-id="67c1f-113">**BlockCount**</span></span><br><span data-ttu-id="67c1f-114">資料類型：Int64</span><span class="sxs-lookup"><span data-stu-id="67c1f-114">Data type: Int64</span></span>|<span data-ttu-id="67c1f-115">實作此參數，讓使用者可以指定區塊計數。</span><span class="sxs-lookup"><span data-stu-id="67c1f-115">Implement this parameter so that the user can specify the block count.</span></span>|
|<span data-ttu-id="67c1f-116">**Count**</span><span class="sxs-lookup"><span data-stu-id="67c1f-116">**Count**</span></span><br><span data-ttu-id="67c1f-117">資料類型：Int64</span><span class="sxs-lookup"><span data-stu-id="67c1f-117">Data type: Int64</span></span>|<span data-ttu-id="67c1f-118">實作此參數，讓使用者可以指定計數。</span><span class="sxs-lookup"><span data-stu-id="67c1f-118">Implement this parameter so that the user can specify the count.</span></span>|
|<span data-ttu-id="67c1f-119">**範圍**</span><span class="sxs-lookup"><span data-stu-id="67c1f-119">**Scope**</span></span><br><span data-ttu-id="67c1f-120">資料類型：關鍵字</span><span class="sxs-lookup"><span data-stu-id="67c1f-120">Data type: Keyword</span></span>|<span data-ttu-id="67c1f-121">實作此參數，讓使用者可以指定要處理的範圍。</span><span class="sxs-lookup"><span data-stu-id="67c1f-121">Implement this parameter so that the user can specify the scope to operate on.</span></span>|

## <a name="see-also"></a><span data-ttu-id="67c1f-122">另請參閱</span><span class="sxs-lookup"><span data-stu-id="67c1f-122">See Also</span></span>

[<span data-ttu-id="67c1f-123">Cmdlet 參數</span><span class="sxs-lookup"><span data-stu-id="67c1f-123">Cmdlet Parameters</span></span>](./cmdlet-parameters.md)

[<span data-ttu-id="67c1f-124">撰寫 Windows PowerShell Cmdlet</span><span class="sxs-lookup"><span data-stu-id="67c1f-124">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)

[<span data-ttu-id="67c1f-125">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="67c1f-125">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)