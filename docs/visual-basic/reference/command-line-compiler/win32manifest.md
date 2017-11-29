---
title: /win32manifest (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- /win32manifest compiler option [Visual Basic]
- win32manifest compiler option [Visual Basic]
- -win32manifest compiler option [Visual Basic]
ms.assetid: 9e3191b4-90db-41c8-966a-28036fd20005
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a46641181c3ff66882468f8372bb97c3a49a8462
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="win32manifest-visual-basic"></a><span data-ttu-id="52551-102">/win32manifest (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="52551-102">/win32manifest (Visual Basic)</span></span>
<span data-ttu-id="52551-103">标识用户定义的 Win32 应用程序清单文件要嵌入到项目的可移植可执行 (PE) 文件。</span><span class="sxs-lookup"><span data-stu-id="52551-103">Identifies a user-defined Win32 application manifest file to be embedded into a project's portable executable (PE) file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52551-104">语法</span><span class="sxs-lookup"><span data-stu-id="52551-104">Syntax</span></span>  
  
```  
/win32manifest: fileName  
```  
  
## <a name="arguments"></a><span data-ttu-id="52551-105">参数</span><span class="sxs-lookup"><span data-stu-id="52551-105">Arguments</span></span>  
  
|<span data-ttu-id="52551-106">术语</span><span class="sxs-lookup"><span data-stu-id="52551-106">Term</span></span>|<span data-ttu-id="52551-107">定义</span><span class="sxs-lookup"><span data-stu-id="52551-107">Definition</span></span>|  
|---|---|  
|`fileName`|<span data-ttu-id="52551-108">自定义清单文件的路径。</span><span class="sxs-lookup"><span data-stu-id="52551-108">The path of the custom manifest file.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="52551-109">备注</span><span class="sxs-lookup"><span data-stu-id="52551-109">Remarks</span></span>  
 <span data-ttu-id="52551-110">默认情况下，Visual Basic 编译器将嵌入指定 asInvoker 的请求的执行级别的应用程序清单。</span><span class="sxs-lookup"><span data-stu-id="52551-110">By default, the Visual Basic compiler embeds an application manifest that specifies a requested execution level of asInvoker.</span></span> <span data-ttu-id="52551-111">它在其中可执行文件的生成，通常的 bin\Debug 或 bin\Release 文件夹时使用 Visual Studio 的相同文件夹中创建清单。</span><span class="sxs-lookup"><span data-stu-id="52551-111">It creates the manifest in the same folder in which the executable file is built, typically the bin\Debug or bin\Release folder when you use Visual Studio.</span></span> <span data-ttu-id="52551-112">如果你想要提供自定义清单，例如，若要指定请求的执行级别的 highestAvailable 或 requireAdministrator，使用此选项以指定文件的名称。</span><span class="sxs-lookup"><span data-stu-id="52551-112">If you want to supply a custom manifest, for example to specify a requested execution level of highestAvailable or requireAdministrator, use this option to specify the name of the file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="52551-113">此选项与[/win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md)选项互斥。</span><span class="sxs-lookup"><span data-stu-id="52551-113">This option and the [/win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md) option are mutually exclusive.</span></span> <span data-ttu-id="52551-114">如果你尝试在相同的命令行中使用这两个选项，则会生成错误。</span><span class="sxs-lookup"><span data-stu-id="52551-114">If you try to use both options in the same command line, you will get a build error.</span></span>  
  
 <span data-ttu-id="52551-115">如果应用程序没有用于指定请求执行级别的应用程序清单，将受到 Windows Vista 的用户帐户控制功能下的文件/注册表虚拟化的影响。</span><span class="sxs-lookup"><span data-stu-id="52551-115">An application that has no application manifest that specifies a requested execution level will be subject to file/registry virtualization under the User Account Control feature in Windows Vista.</span></span> <span data-ttu-id="52551-116">有关虚拟化的详细信息，请参阅[ClickOnce 部署在 Windows Vista 上](/visualstudio/deployment/clickonce-deployment-on-windows-vista)。</span><span class="sxs-lookup"><span data-stu-id="52551-116">For more information about virtualization, see [ClickOnce Deployment on Windows Vista](/visualstudio/deployment/clickonce-deployment-on-windows-vista).</span></span>  
  
 <span data-ttu-id="52551-117">如果以下条件之一为 true，你的应用程序都将遵循虚拟化：</span><span class="sxs-lookup"><span data-stu-id="52551-117">Your application will be subject to virtualization if either of the following conditions is true:</span></span>  
  
1.  <span data-ttu-id="52551-118">你使用`/nowin32manifest`选项，你不提供清单中的更高版本的生成步骤或 Windows 资源 (.res) 文件的一部分使用`/win32resource`选项。</span><span class="sxs-lookup"><span data-stu-id="52551-118">You use the `/nowin32manifest` option and you do not provide a manifest in a later build step or as part of a Windows Resource (.res) file by using the `/win32resource` option.</span></span>  
  
2.  <span data-ttu-id="52551-119">提供的自定义清单未指定请求执行级别。</span><span class="sxs-lookup"><span data-stu-id="52551-119">You provide a custom manifest that does not specify a requested execution level.</span></span>  
  
 [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)]<span data-ttu-id="52551-120"> 创建默认的 .manifest 文件，并将该文件与可执行文件一起存储在 debug 和 release 目录中。</span><span class="sxs-lookup"><span data-stu-id="52551-120"> creates a default .manifest file and stores it in the debug and release directories alongside the executable file.</span></span> <span data-ttu-id="52551-121">你可以查看或通过单击编辑默认应用程序清单文件**视图 UAC 设置**上**应用程序**项目设计器中的选项卡。</span><span class="sxs-lookup"><span data-stu-id="52551-121">You can view or edit the default app.manifest file by clicking **View UAC Settings** on the **Application** tab in the Project Designer.</span></span> <span data-ttu-id="52551-122">有关详细信息，请参阅 [Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic)（应用程序页、项目设计器 (Visual Basic)。</span><span class="sxs-lookup"><span data-stu-id="52551-122">For more information, see [Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic).</span></span>  
  
 <span data-ttu-id="52551-123">你可以提供应用程序清单作为自定义的生成后步骤或 Win32 资源文件的一部分使用`/nowin32manifest`选项。</span><span class="sxs-lookup"><span data-stu-id="52551-123">You can provide the application manifest as a custom post-build step or as part of a Win32 resource file by using the `/nowin32manifest` option.</span></span> <span data-ttu-id="52551-124">如果希望应用程序受到 Windows Vista 的文件或注册表虚拟化的影响，请使用该选项。</span><span class="sxs-lookup"><span data-stu-id="52551-124">Use that same option if you want your application to be subject to file or registry virtualization on Windows Vista.</span></span> <span data-ttu-id="52551-125">这将使编译器无法创建和嵌入在 PE 文件中的默认清单。</span><span class="sxs-lookup"><span data-stu-id="52551-125">This will prevent the compiler from creating and embedding a default manifest in the PE file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="52551-126">示例</span><span class="sxs-lookup"><span data-stu-id="52551-126">Example</span></span>  
 <span data-ttu-id="52551-127">下面的示例演示了 Visual Basic 编译器将插入 PE 默认清单。</span><span class="sxs-lookup"><span data-stu-id="52551-127">The following example shows the default manifest that the Visual Basic compiler inserts into a PE.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="52551-128">编译器将插入清单 XML 的标准应用程序名称 MyApplication.app。</span><span class="sxs-lookup"><span data-stu-id="52551-128">The compiler inserts a standard application name MyApplication.app into the manifest XML.</span></span> <span data-ttu-id="52551-129">这是一种使应用程序可以在 Windows Server 2003 Service Pack 3 上运行的解决方法。</span><span class="sxs-lookup"><span data-stu-id="52551-129">This is a workaround to enable applications to run on Windows Server 2003 Service Pack 3.</span></span>  
  
```xml  
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
  
## <a name="see-also"></a><span data-ttu-id="52551-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="52551-130">See Also</span></span>  
 [<span data-ttu-id="52551-131">Visual Basic 命令行编译器</span><span class="sxs-lookup"><span data-stu-id="52551-131">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="52551-132">/nowin32manifest (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="52551-132">/nowin32manifest (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/nowin32manifest.md)
