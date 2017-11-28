---
title: "-nowin32manifest（C# 编译器选项）"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: /nowin32manifest
helpviewer_keywords:
- nowin32manifest compiler option [C#]
- -nowin32manifest compiler option [C#]
- /nowin32manifest compiler option [C#]
ms.assetid: 6f06365b-b87b-46a2-b187-b3bfeaf4862d
caps.latest.revision: "15"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 1e0d4697e0e14c84c4bc642521cf4f9cdf6a4ed6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="nowin32manifest-c-compiler-options"></a><span data-ttu-id="b0715-102">/nowin32manifest（C# 编译器选项）</span><span class="sxs-lookup"><span data-stu-id="b0715-102">/nowin32manifest (C# Compiler Options)</span></span>
<span data-ttu-id="b0715-103">使用 **/nowin32manifest** 选项可指示编译器不将任何应用程序清单嵌入到可执行文件中。</span><span class="sxs-lookup"><span data-stu-id="b0715-103">Use the **/nowin32manifest** option to instruct the compiler not to embed any application manifest into the executable file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b0715-104">语法</span><span class="sxs-lookup"><span data-stu-id="b0715-104">Syntax</span></span>  
  
```console  
/nowin32manifest  
```  
  
## <a name="remarks"></a><span data-ttu-id="b0715-105">备注</span><span class="sxs-lookup"><span data-stu-id="b0715-105">Remarks</span></span>  
 <span data-ttu-id="b0715-106">使用此选项时，除非在 Win32 资源文件或以后的生成步骤中提供应用程序清单，否则应用程序会受到 Windows Vista 上虚拟化的影响。</span><span class="sxs-lookup"><span data-stu-id="b0715-106">When this option is used, the application will be subject to virtualization on Windows Vista unless you provide an application manifest in a Win32 Resource file or during a later build step.</span></span>  
  
 <span data-ttu-id="b0715-107">在 Visual Studio 的“应用程序属性”页中，通过在“清单”下拉列表中选择“创建不带清单的应用程序”选项来设置此选项。</span><span class="sxs-lookup"><span data-stu-id="b0715-107">In Visual Studio, set this option in the **Application Property** page by selecting the **Create Application Without a Manifest** option in the **Manifest** drop down list.</span></span> <span data-ttu-id="b0715-108">有关详细信息，请参阅[“项目设计器”->“应用程序”页 (C#)](/visualstudio/ide/reference/application-page-project-designer-csharp)。</span><span class="sxs-lookup"><span data-stu-id="b0715-108">For more information, see [Application Page, Project Designer (C#)](/visualstudio/ide/reference/application-page-project-designer-csharp).</span></span>  
  
 <span data-ttu-id="b0715-109">有关创建清单的详细信息，请参阅 [/win32manifest（C# 编译器选项）](../../../csharp/language-reference/compiler-options/win32manifest-compiler-option.md)。</span><span class="sxs-lookup"><span data-stu-id="b0715-109">For more information about manifest creation, see [/win32manifest (C# Compiler Options)](../../../csharp/language-reference/compiler-options/win32manifest-compiler-option.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0715-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b0715-110">See Also</span></span>  
 [<span data-ttu-id="b0715-111">C# 编译器选项</span><span class="sxs-lookup"><span data-stu-id="b0715-111">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)  
 [<span data-ttu-id="b0715-112">管理项目和解决方案属性</span><span class="sxs-lookup"><span data-stu-id="b0715-112">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
