---
title: 如何設定 HelpInfo XML 版本號碼 |Microsoft Docs
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 93a00463-af58-41c8-b088-450909fa1d05
caps.latest.revision: 6
ms.openlocfilehash: b98e6879bbfe0e3ec1a9ab37496dde44caf523a4
ms.sourcegitcommit: caac7d098a448232304c9d6728e7340ec7517a71
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/16/2019
ms.locfileid: "58054130"
---
# <a name="how-to-set-helpinfo-xml-version-numbers"></a><span data-ttu-id="47cf6-102">如何設定 HelpInfo XML 版本號碼</span><span class="sxs-lookup"><span data-stu-id="47cf6-102">How to Set HelpInfo XML Version Numbers</span></span>

<span data-ttu-id="47cf6-103">本主題說明如何設定及增加版本號碼，在可更新的說明資訊檔案中，通常稱為 「 HelpInfo XML 檔案 」。</span><span class="sxs-lookup"><span data-stu-id="47cf6-103">This topic explains how to set and increase the version numbers in an Updatable Help Information file, commonly known as a "HelpInfo XML file."</span></span>

## <a name="how-to-set-helpinfo-xml-version-numbers"></a><span data-ttu-id="47cf6-104">如何設定 HelpInfo XML 版本號碼</span><span class="sxs-lookup"><span data-stu-id="47cf6-104">How to Set HelpInfo XML Version Numbers</span></span>

<span data-ttu-id="47cf6-105">HelpInfo XML 檔案中的版本號碼操作是很重要的可更新的說明。</span><span class="sxs-lookup"><span data-stu-id="47cf6-105">The version numbers in a HelpInfo XML file are critical to the operation of Updatable Help.</span></span>
<span data-ttu-id="47cf6-106">[Update-help](/powershell/module/Microsoft.PowerShell.Core/Update-Help)並[Save-help](/powershell/module/Microsoft.PowerShell.Core/Save-Help) cmdlet 在遠端 HelpInfo XML 檔案中的 UI 文化特性的版本號碼大於該 UI 文化特性的版本號碼時，才下載新的說明檔本機 HelpInfo XML，或沒有本機 HelpInfo XML 檔案。</span><span class="sxs-lookup"><span data-stu-id="47cf6-106">The [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) and [Save-Help](/powershell/module/Microsoft.PowerShell.Core/Save-Help) cmdlets download new help files only when the version number for a UI culture in the remote HelpInfo XML file is greater than the version number for that UI culture in the local HelpInfo XML, or there is no local HelpInfo XML file.</span></span>

<span data-ttu-id="47cf6-107">HelpInfo XML 檔案會使用定義於 4 部分版本號碼**System.Version**的 Microsoft.NET Framework 類別。</span><span class="sxs-lookup"><span data-stu-id="47cf6-107">The HelpInfo XML file uses the 4-part version number that is defined in the **System.Version** class of the Microsoft .NET Framework.</span></span> <span data-ttu-id="47cf6-108">格式是`N1.N2.N3.N4`。</span><span class="sxs-lookup"><span data-stu-id="47cf6-108">The format is `N1.N2.N3.N4`.</span></span> <span data-ttu-id="47cf6-109">模組作者可以使用編號配置所允許的任何版本**System.Version**類別。</span><span class="sxs-lookup"><span data-stu-id="47cf6-109">Module authors can use any version numbering scheme that is permitted by the **System.Version** class.</span></span> <span data-ttu-id="47cf6-110">可更新的說明，只有版本號碼 UI 文化特性增加時需要新版的 UI 文化特性的 CAB 檔案上傳至所指定的位置**HelpContentURI** HelpInfo XML 檔案中的項目。</span><span class="sxs-lookup"><span data-stu-id="47cf6-110">Updatable Help requires only that the version number for a UI culture increase when a new version of the CAB file for that UI culture is uploaded to the location that is specified by the **HelpContentURI** element in the HelpInfo XML file.</span></span>

<span data-ttu-id="47cf6-111">下列範例顯示德文 (DE-DE) UI 文化特性的版本時 2.15.0.10 HelpInfo XML 檔案的項目。</span><span class="sxs-lookup"><span data-stu-id="47cf6-111">The following example shows the elements of the HelpInfo XML file for the German (de-DE) UI culture when the version is 2.15.0.10.</span></span>

```xml

<UICulture>
  <UICultureName>de-DE</UICultureName>
  <UICultureVersion>2.15.0.10</UICultureVersion>
</UICulture>
```

<span data-ttu-id="47cf6-112">UI 文化特性的版本號碼會反映該 UI 文化特性的 CAB 檔案的版本。</span><span class="sxs-lookup"><span data-stu-id="47cf6-112">The version number for a UI culture reflects the version of the CAB file for that UI culture.</span></span> <span data-ttu-id="47cf6-113">版本號碼套用到整個封包檔。</span><span class="sxs-lookup"><span data-stu-id="47cf6-113">The version number applies to the entire CAB file.</span></span> <span data-ttu-id="47cf6-114">您無法在封包檔中設定不同的版本號碼不同的檔案。</span><span class="sxs-lookup"><span data-stu-id="47cf6-114">You cannot set different version numbers for different files in the CAB file.</span></span> <span data-ttu-id="47cf6-115">版本號碼，每個 UI 文化特性獨立進行評估，並不需要與相關的其他模組支援的 UI 文化特性的版本號碼。</span><span class="sxs-lookup"><span data-stu-id="47cf6-115">The version number for each UI culture is evaluated independently and need not be related to the version numbers for other UI cultures that the module supports.</span></span>