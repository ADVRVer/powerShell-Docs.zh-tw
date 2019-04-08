---
title: 設定參數的格式 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 10e025c5-9aa6-45a5-b851-23d14db1f4cc
caps.latest.revision: 7
ms.openlocfilehash: 0bd3888d81aa6d1dde26c0066f7bca9dac8a8bca
ms.sourcegitcommit: ce46e5098786e19d521b4bf948ff62d2b90bc53e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/02/2019
ms.locfileid: "57251178"
---
# <a name="format-parameters"></a><span data-ttu-id="6821b-102">格式參數</span><span class="sxs-lookup"><span data-stu-id="6821b-102">Format Parameters</span></span>

<span data-ttu-id="6821b-103">下表列出建議的名稱和參數，可用來格式化，或產生資料的功能。</span><span class="sxs-lookup"><span data-stu-id="6821b-103">The following table lists recommended names and functionality for parameters that are used to format or to generate data.</span></span>

|<span data-ttu-id="6821b-104">參數</span><span class="sxs-lookup"><span data-stu-id="6821b-104">Parameter</span></span>|<span data-ttu-id="6821b-105">功能</span><span class="sxs-lookup"><span data-stu-id="6821b-105">Functionality</span></span>|
|---|---|
|<span data-ttu-id="6821b-106">**As**</span><span class="sxs-lookup"><span data-stu-id="6821b-106">**As**</span></span><br><span data-ttu-id="6821b-107">資料類型：關鍵字</span><span class="sxs-lookup"><span data-stu-id="6821b-107">Data type: Keyword</span></span>|<span data-ttu-id="6821b-108">實作這個參數來指定 cmdlet 的輸出格式。</span><span class="sxs-lookup"><span data-stu-id="6821b-108">Implement this parameter to specify the cmdlet output format.</span></span> <span data-ttu-id="6821b-109">例如，文字或指令碼，可能是可能的值。</span><span class="sxs-lookup"><span data-stu-id="6821b-109">For example, possible values could be Text or Script.</span></span>|
|<span data-ttu-id="6821b-110">**二進位檔**</span><span class="sxs-lookup"><span data-stu-id="6821b-110">**Binary**</span></span><br><span data-ttu-id="6821b-111">資料類型：SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="6821b-111">Data type: SwitchParameter</span></span>|<span data-ttu-id="6821b-112">實作此參數，以指出此 cmdlet 會處理二進位值。</span><span class="sxs-lookup"><span data-stu-id="6821b-112">Implement this parameter to indicate that the cmdlet handles binary values.</span></span>|
|<span data-ttu-id="6821b-113">**編碼方式**</span><span class="sxs-lookup"><span data-stu-id="6821b-113">**Encoding**</span></span><br><span data-ttu-id="6821b-114">資料類型：關鍵字</span><span class="sxs-lookup"><span data-stu-id="6821b-114">Data type: Keyword</span></span>|<span data-ttu-id="6821b-115">實作這個參數來指定支援的編碼類型。</span><span class="sxs-lookup"><span data-stu-id="6821b-115">Implement this parameter to specify the type of encoding that is supported.</span></span> <span data-ttu-id="6821b-116">例如，ASCII、 UTF8、 Unicode、 UTF7、 BigEndianUnicode、 位元組、 和字串，可能是可能的值。</span><span class="sxs-lookup"><span data-stu-id="6821b-116">For example, possible values could be ASCII, UTF8, Unicode, UTF7, BigEndianUnicode, Byte, and String.</span></span>|
|<span data-ttu-id="6821b-117">**NewLine**</span><span class="sxs-lookup"><span data-stu-id="6821b-117">**NewLine**</span></span><br><span data-ttu-id="6821b-118">資料類型：SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="6821b-118">Data type: SwitchParameter</span></span>|<span data-ttu-id="6821b-119">實作此參數，參數會指定時，才支援新行字元。</span><span class="sxs-lookup"><span data-stu-id="6821b-119">Implement this parameter so that the newline characters are supported when the parameter is specified.</span></span>|
|<span data-ttu-id="6821b-120">**ShortName**</span><span class="sxs-lookup"><span data-stu-id="6821b-120">**ShortName**</span></span><br><span data-ttu-id="6821b-121">資料類型：SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="6821b-121">Data type: SwitchParameter</span></span>|<span data-ttu-id="6821b-122">實作此參數，參數會指定時，才支援短檔名。</span><span class="sxs-lookup"><span data-stu-id="6821b-122">Implement this parameter so that short names are supported when the parameter is specified.</span></span>|
|<span data-ttu-id="6821b-123">**Width**</span><span class="sxs-lookup"><span data-stu-id="6821b-123">**Width**</span></span><br><span data-ttu-id="6821b-124">資料類型：Int32</span><span class="sxs-lookup"><span data-stu-id="6821b-124">Data type: Int32</span></span>|<span data-ttu-id="6821b-125">實作此參數，讓使用者可以指定輸出裝置的寬度。</span><span class="sxs-lookup"><span data-stu-id="6821b-125">Implement this parameter so that the user can specify the width of the output device.</span></span>|
|<span data-ttu-id="6821b-126">**Wrap**</span><span class="sxs-lookup"><span data-stu-id="6821b-126">**Wrap**</span></span><br><span data-ttu-id="6821b-127">資料類型：SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="6821b-127">Data type: SwitchParameter</span></span>|<span data-ttu-id="6821b-128">實作此參數，指定此參數時，支援文字換行。</span><span class="sxs-lookup"><span data-stu-id="6821b-128">Implement this parameter so that text wrapping is supported when the parameter is specified.</span></span>|
## <a name="see-also"></a><span data-ttu-id="6821b-129">另請參閱</span><span class="sxs-lookup"><span data-stu-id="6821b-129">See Also</span></span>

[<span data-ttu-id="6821b-130">Cmdlet 參數</span><span class="sxs-lookup"><span data-stu-id="6821b-130">Cmdlet Parameters</span></span>](./cmdlet-parameters.md)

[<span data-ttu-id="6821b-131">撰寫 Windows PowerShell Cmdlet</span><span class="sxs-lookup"><span data-stu-id="6821b-131">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)

[<span data-ttu-id="6821b-132">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="6821b-132">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)