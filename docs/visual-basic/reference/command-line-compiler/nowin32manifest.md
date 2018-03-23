---
title: -nowin32manifest (Visual Basic)
ms.date: 03/13/2018
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- /nowin32manifest compiler option [Visual Basic]
- nowin32manifest compiler option [Visual Basic]
- -nowin32manifest compiler option [Visual Basic]
ms.assetid: c0528aae-83b3-4425-99f0-19448e9843e3
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7c539f7833c86215a1b0f8102f9fc46419636bc7
ms.sourcegitcommit: 498799639937c89de777361aab74261efe7b79ea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/22/2018
---
# <a name="-nowin32manifest-visual-basic"></a><span data-ttu-id="4b3cc-102">-nowin32manifest (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4b3cc-102">-nowin32manifest (Visual Basic)</span></span>
<span data-ttu-id="4b3cc-103">指示编译器不在可执行文件中嵌入任何应用程序清单。</span><span class="sxs-lookup"><span data-stu-id="4b3cc-103">Instructs the compiler not to embed any application manifest into the executable file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4b3cc-104">语法</span><span class="sxs-lookup"><span data-stu-id="4b3cc-104">Syntax</span></span>  
  
```  
-nowin32manifest  
```  
  
## <a name="remarks"></a><span data-ttu-id="4b3cc-105">备注</span><span class="sxs-lookup"><span data-stu-id="4b3cc-105">Remarks</span></span>  
 <span data-ttu-id="4b3cc-106">使用此选项时，除非在 Win32 资源文件或以后的生成步骤中提供应用程序清单，否则应用程序会受到 Windows Vista 上虚拟化的影响。</span><span class="sxs-lookup"><span data-stu-id="4b3cc-106">When this option is used, the application will be subject to virtualization on Windows Vista unless you provide an application manifest in a Win32 Resource file or during a later build step.</span></span> <span data-ttu-id="4b3cc-107">有关虚拟化的详细信息，请参阅[ClickOnce 部署在 Windows Vista 上](/visualstudio/deployment/clickonce-deployment-on-windows-vista)。</span><span class="sxs-lookup"><span data-stu-id="4b3cc-107">For more information about virtualization, see [ClickOnce Deployment on Windows Vista](/visualstudio/deployment/clickonce-deployment-on-windows-vista).</span></span>  
  
 <span data-ttu-id="4b3cc-108">有关创建清单的详细信息，请参阅[-win32manifest (Visual Basic 中)](../../../visual-basic/reference/command-line-compiler/win32manifest.md)。</span><span class="sxs-lookup"><span data-stu-id="4b3cc-108">For more information about manifest creation, see [-win32manifest (Visual Basic)](../../../visual-basic/reference/command-line-compiler/win32manifest.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b3cc-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4b3cc-109">See Also</span></span>  
 [<span data-ttu-id="4b3cc-110">Visual Basic 命令行编译器</span><span class="sxs-lookup"><span data-stu-id="4b3cc-110">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="4b3cc-111">“项目设计器”->“应用程序”页 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4b3cc-111">Application Page, Project Designer (Visual Basic)</span></span>](/visualstudio/ide/reference/application-page-project-designer-visual-basic)
