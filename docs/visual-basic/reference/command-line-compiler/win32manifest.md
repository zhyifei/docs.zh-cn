---
title: "/win32manifest (Visual Basic 中) |Microsoft 文档"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- /win32manifest compiler option [Visual Basic]
- win32manifest compiler option [Visual Basic]
- -win32manifest compiler option [Visual Basic]
ms.assetid: 9e3191b4-90db-41c8-966a-28036fd20005
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 4a9693bd7eb03dee5a2a9f2d43360b963e9fd876
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="win32manifest-visual-basic"></a><span data-ttu-id="d7e34-102">/win32manifest (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d7e34-102">/win32manifest (Visual Basic)</span></span>
<span data-ttu-id="d7e34-103">标识用户定义的 Win32 应用程序清单文件要嵌入到项目的可移植可执行 (PE) 文件。</span><span class="sxs-lookup"><span data-stu-id="d7e34-103">Identifies a user-defined Win32 application manifest file to be embedded into a project's portable executable (PE) file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d7e34-104">语法</span><span class="sxs-lookup"><span data-stu-id="d7e34-104">Syntax</span></span>  
  
```  
/win32manifest: fileName  
```  
  
## <a name="arguments"></a><span data-ttu-id="d7e34-105">参数</span><span class="sxs-lookup"><span data-stu-id="d7e34-105">Arguments</span></span>  
  
|<span data-ttu-id="d7e34-106">术语</span><span class="sxs-lookup"><span data-stu-id="d7e34-106">Term</span></span>|<span data-ttu-id="d7e34-107">定义</span><span class="sxs-lookup"><span data-stu-id="d7e34-107">Definition</span></span>|  
|---|---|  
|`fileName`|<span data-ttu-id="d7e34-108">自定义清单文件的路径。</span><span class="sxs-lookup"><span data-stu-id="d7e34-108">The path of the custom manifest file.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d7e34-109">备注</span><span class="sxs-lookup"><span data-stu-id="d7e34-109">Remarks</span></span>  
 <span data-ttu-id="d7e34-110">默认情况下，Visual Basic 编译器将嵌入到指定 asInvoker 请求的执行级别的应用程序清单。</span><span class="sxs-lookup"><span data-stu-id="d7e34-110">By default, the Visual Basic compiler embeds an application manifest that specifies a requested execution level of asInvoker.</span></span> <span data-ttu-id="d7e34-111">它在其中可执行文件生成，通常为 bin\Debug 或 bin\Release 文件夹时使用 Visual Studio 的相同文件夹中创建清单。</span><span class="sxs-lookup"><span data-stu-id="d7e34-111">It creates the manifest in the same folder in which the executable file is built, typically the bin\Debug or bin\Release folder when you use Visual Studio.</span></span> <span data-ttu-id="d7e34-112">如果您想要提供自定义清单，例如，若要指定请求的执行级别的 highestAvailable 或 requireAdministrator，使用此选项以指定文件的名称。</span><span class="sxs-lookup"><span data-stu-id="d7e34-112">If you want to supply a custom manifest, for example to specify a requested execution level of highestAvailable or requireAdministrator, use this option to specify the name of the file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d7e34-113">此选项与[/win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md)是互相排斥的选项。</span><span class="sxs-lookup"><span data-stu-id="d7e34-113">This option and the [/win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md) option are mutually exclusive.</span></span> <span data-ttu-id="d7e34-114">如果您尝试在同一命令行中使用这两个选项，则会生成错误。</span><span class="sxs-lookup"><span data-stu-id="d7e34-114">If you try to use both options in the same command line, you will get a build error.</span></span>  
  
 <span data-ttu-id="d7e34-115">没有应用程序清单，应用程序指定的请求的执行级别都将遵循在 Windows Vista 中的用户帐户控制功能下的文件/注册表虚拟化。</span><span class="sxs-lookup"><span data-stu-id="d7e34-115">An application that has no application manifest that specifies a requested execution level will be subject to file/registry virtualization under the User Account Control feature in Windows Vista.</span></span> <span data-ttu-id="d7e34-116">有关虚拟化的详细信息，请参阅[Windows Vista 上的 ClickOnce 部署](https://docs.microsoft.com/visualstudio/deployment/clickonce-deployment-on-windows-vista)。</span><span class="sxs-lookup"><span data-stu-id="d7e34-116">For more information about virtualization, see [ClickOnce Deployment on Windows Vista](https://docs.microsoft.com/visualstudio/deployment/clickonce-deployment-on-windows-vista).</span></span>  
  
 <span data-ttu-id="d7e34-117">如果任意下列条件为真，您的应用程序将遵循虚拟化︰</span><span class="sxs-lookup"><span data-stu-id="d7e34-117">Your application will be subject to virtualization if either of the following conditions is true:</span></span>  
  
1.  <span data-ttu-id="d7e34-118">您使用`/nowin32manifest`选项，你不提供清单在更高版本的生成步骤或 Windows 资源 (.res) 文件的一部分使用`/win32resource`选项。</span><span class="sxs-lookup"><span data-stu-id="d7e34-118">You use the `/nowin32manifest` option and you do not provide a manifest in a later build step or as part of a Windows Resource (.res) file by using the `/win32resource` option.</span></span>  
  
2.  <span data-ttu-id="d7e34-119">提供一个自定义清单，不指定请求的执行级别。</span><span class="sxs-lookup"><span data-stu-id="d7e34-119">You provide a custom manifest that does not specify a requested execution level.</span></span>  
  
 [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)]<span data-ttu-id="d7e34-120">创建一个默认.manifest 文件并将其存储在可执行文件旁的调试和发布目录。</span><span class="sxs-lookup"><span data-stu-id="d7e34-120"> creates a default .manifest file and stores it in the debug and release directories alongside the executable file.</span></span> <span data-ttu-id="d7e34-121">您可以查看或编辑默认应用程序清单文件，方法是单击**视图 UAC 设置**上**应用程序**项目设计器中的选项卡。</span><span class="sxs-lookup"><span data-stu-id="d7e34-121">You can view or edit the default app.manifest file by clicking **View UAC Settings** on the **Application** tab in the Project Designer.</span></span> <span data-ttu-id="d7e34-122">有关详细信息，请参阅[应用程序页，项目设计器 (Visual Basic 中)](https://docs.microsoft.com/visualstudio/ide/reference/application-page-project-designer-visual-basic)。</span><span class="sxs-lookup"><span data-stu-id="d7e34-122">For more information, see [Application Page, Project Designer (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/application-page-project-designer-visual-basic).</span></span>  
  
 <span data-ttu-id="d7e34-123">您可以通过使用提供的应用程序清单作为自定义后期生成步骤或作为 Win32 资源文件的一部分`/nowin32manifest`选项。</span><span class="sxs-lookup"><span data-stu-id="d7e34-123">You can provide the application manifest as a custom post-build step or as part of a Win32 resource file by using the `/nowin32manifest` option.</span></span> <span data-ttu-id="d7e34-124">如果您希望应用程序会受到在 Windows Vista 上的文件或注册表虚拟化，使用该相同的选项。</span><span class="sxs-lookup"><span data-stu-id="d7e34-124">Use that same option if you want your application to be subject to file or registry virtualization on Windows Vista.</span></span> <span data-ttu-id="d7e34-125">这将使编译器创建和嵌入在 PE 文件中的默认清单。</span><span class="sxs-lookup"><span data-stu-id="d7e34-125">This will prevent the compiler from creating and embedding a default manifest in the PE file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d7e34-126">示例</span><span class="sxs-lookup"><span data-stu-id="d7e34-126">Example</span></span>  
 <span data-ttu-id="d7e34-127">下面的示例演示了 Visual Basic 编译器将插入 PE 默认清单。</span><span class="sxs-lookup"><span data-stu-id="d7e34-127">The following example shows the default manifest that the Visual Basic compiler inserts into a PE.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d7e34-128">编译器将插入清单 XML 的标准应用程序名称 MyApplication.app。</span><span class="sxs-lookup"><span data-stu-id="d7e34-128">The compiler inserts a standard application name MyApplication.app into the manifest XML.</span></span> <span data-ttu-id="d7e34-129">这是一种解决方法，使应用程序可以在 Windows Server 2003 Service Pack 3 上运行。</span><span class="sxs-lookup"><span data-stu-id="d7e34-129">This is a workaround to enable applications to run on Windows Server 2003 Service Pack 3.</span></span>  
  
```  
<?xml version="1.0" encoding="utf-8" standalone="yes"?>  
<assembly xmlns="urn:schemas-microsoft-com:asm.v1" manifestVersion="1.0">  
  <assemblyIdentity version="1.0.0.0" name="MyApplication.app"/>  
  <trustInfo xmlns="urn:schemas-microsoft-com:asm.v2">  
    <security>  
      <requestedPrivileges xmlns="urn:schemas-microsoft-com:asm.v3">  
        <requestedExecutionLevel level="asInvoker"/>  
      </requestedPrivileges>  
    </security>  
  </trustInfo>  
</assembly>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d7e34-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d7e34-130">See Also</span></span>  
 <span data-ttu-id="d7e34-131">[Visual Basic 命令行编译器](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="d7e34-131">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="d7e34-132"> [/nowin32manifest (Visual Basic)](../../../visual-basic/reference/command-line-compiler/nowin32manifest.md)</span><span class="sxs-lookup"><span data-stu-id="d7e34-132"> [/nowin32manifest (Visual Basic)](../../../visual-basic/reference/command-line-compiler/nowin32manifest.md)</span></span>
