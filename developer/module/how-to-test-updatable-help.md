---
title: 如何測試可更新的說明 |Microsoft Docs
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3e064048-2b94-4365-bdb7-f1ee7c0a7fd7
caps.latest.revision: 6
ms.openlocfilehash: cecc6c26ccaece06462ddd74b53534137fcf3037
ms.sourcegitcommit: 5990f04b8042ef2d8e571bec6d5b051e64c9921c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/12/2019
ms.locfileid: "57794258"
---
# <a name="how-to-test-updatable-help"></a><span data-ttu-id="c35bd-102">如何測試可更新的說明</span><span class="sxs-lookup"><span data-stu-id="c35bd-102">How to Test Updatable Help</span></span>

<span data-ttu-id="c35bd-103">本主題描述若要測試之模組的 可更新說明的方法。</span><span class="sxs-lookup"><span data-stu-id="c35bd-103">This topic describes approaches to testing Updatable Help for a module.</span></span>

## <a name="using-verbose-to-detect-errors"></a><span data-ttu-id="c35bd-104">使用詳細資訊，以偵測錯誤</span><span class="sxs-lookup"><span data-stu-id="c35bd-104">Using Verbose to Detect Errors</span></span>

<span data-ttu-id="c35bd-105">上傳後 HelpInfo XML 檔案和封包檔的模組，來測試檔案執行[Update-help](/powershell/module/Microsoft.PowerShell.Core/Update-Help)命令搭配**Verbose**參數。</span><span class="sxs-lookup"><span data-stu-id="c35bd-105">After uploading the HelpInfo XML file and CAB files for your module, test the files by running an [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) command with the **Verbose** parameter.</span></span> <span data-ttu-id="c35bd-106">**Verbose**參數會指示`Update-Help`回報其動作，讀取的重要步驟**HelpInfoUri**驗證解除封裝的封包檔中的檔案類型的模組資訊清單中的索引鍵並將這些檔案放在特定語言的模組目錄中。</span><span class="sxs-lookup"><span data-stu-id="c35bd-106">The **Verbose** parameter directs `Update-Help` to report the critical steps in its actions, from reading the **HelpInfoUri** key in the module manifest to validating the file types in the unpacked CAB file and placing the files in the language-specific module directory.</span></span>

<span data-ttu-id="c35bd-107">解析所有的詳細資訊訊息時，執行`Update-Help`命令搭配**偵錯**參數。</span><span class="sxs-lookup"><span data-stu-id="c35bd-107">When all verbose messages are resolved, run an `Update-Help` command with the **Debug** parameter.</span></span> <span data-ttu-id="c35bd-108">這個參數應該會偵測任何剩餘的問題，可更新的說明檔案。</span><span class="sxs-lookup"><span data-stu-id="c35bd-108">This parameter should detect any remaining problems with the Updatable Help files.</span></span>