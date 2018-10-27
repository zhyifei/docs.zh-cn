---
title: -win32manifest (Visual Basic)
ms.date: 03/13/2018
helpviewer_keywords:
- /win32manifest compiler option [Visual Basic]
- win32manifest compiler option [Visual Basic]
- -win32manifest compiler option [Visual Basic]
ms.assetid: 9e3191b4-90db-41c8-966a-28036fd20005
ms.openlocfilehash: 1982a70c4baacae5ffb35efd93d447c4d81b00b5
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2018
ms.locfileid: "50181103"
---
# <a name="-win32manifest-visual-basic"></a><span data-ttu-id="dd720-102">-win32manifest (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="dd720-102">-win32manifest (Visual Basic)</span></span>
<span data-ttu-id="dd720-103">标识用户定义的 Win32 应用程序清单文件要嵌入到项目的可移植可执行 (PE) 文件。</span><span class="sxs-lookup"><span data-stu-id="dd720-103">Identifies a user-defined Win32 application manifest file to be embedded into a project's portable executable (PE) file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dd720-104">语法</span><span class="sxs-lookup"><span data-stu-id="dd720-104">Syntax</span></span>  
  
```  
-win32manifest: fileName  
```  
  
## <a name="arguments"></a><span data-ttu-id="dd720-105">自变量</span><span class="sxs-lookup"><span data-stu-id="dd720-105">Arguments</span></span>  
  
|<span data-ttu-id="dd720-106">术语</span><span class="sxs-lookup"><span data-stu-id="dd720-106">Term</span></span>|<span data-ttu-id="dd720-107">定义</span><span class="sxs-lookup"><span data-stu-id="dd720-107">Definition</span></span>|  
|---|---|  
|`fileName`|<span data-ttu-id="dd720-108">自定义清单文件的路径。</span><span class="sxs-lookup"><span data-stu-id="dd720-108">The path of the custom manifest file.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dd720-109">备注</span><span class="sxs-lookup"><span data-stu-id="dd720-109">Remarks</span></span>  
 <span data-ttu-id="dd720-110">默认情况下，Visual Basic 编译器嵌入指定 asInvoker 的请求的执行级别的应用程序清单。</span><span class="sxs-lookup"><span data-stu-id="dd720-110">By default, the Visual Basic compiler embeds an application manifest that specifies a requested execution level of asInvoker.</span></span> <span data-ttu-id="dd720-111">它在其中可执行文件生成，通常使用 Visual Studio 时的 bin\Debug 或 bin\Release 文件夹位于同一文件夹中创建清单。</span><span class="sxs-lookup"><span data-stu-id="dd720-111">It creates the manifest in the same folder in which the executable file is built, typically the bin\Debug or bin\Release folder when you use Visual Studio.</span></span> <span data-ttu-id="dd720-112">如果你想要提供自定义清单，例如若要指定请求的执行级别的最高可用性或 requireAdministrator，使用此选项以指定的文件的名称。</span><span class="sxs-lookup"><span data-stu-id="dd720-112">If you want to supply a custom manifest, for example to specify a requested execution level of highestAvailable or requireAdministrator, use this option to specify the name of the file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dd720-113">此选项和[-win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md)是互斥的选项。</span><span class="sxs-lookup"><span data-stu-id="dd720-113">This option and the [-win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md) option are mutually exclusive.</span></span> <span data-ttu-id="dd720-114">如果尝试在同一命令行中使用这两个选项，则会生成错误。</span><span class="sxs-lookup"><span data-stu-id="dd720-114">If you try to use both options in the same command line, you will get a build error.</span></span>  
  
 <span data-ttu-id="dd720-115">如果应用程序没有用于指定请求执行级别的应用程序清单，将受到 Windows Vista 的用户帐户控制功能下的文件/注册表虚拟化的影响。</span><span class="sxs-lookup"><span data-stu-id="dd720-115">An application that has no application manifest that specifies a requested execution level will be subject to file/registry virtualization under the User Account Control feature in Windows Vista.</span></span> <span data-ttu-id="dd720-116">有关虚拟化的详细信息，请参阅[Windows Vista 上的 ClickOnce 部署](/visualstudio/deployment/clickonce-deployment-on-windows-vista)。</span><span class="sxs-lookup"><span data-stu-id="dd720-116">For more information about virtualization, see [ClickOnce Deployment on Windows Vista](/visualstudio/deployment/clickonce-deployment-on-windows-vista).</span></span>  
  
 <span data-ttu-id="dd720-117">如果以下条件之一为 true，你的应用程序会受到虚拟化：</span><span class="sxs-lookup"><span data-stu-id="dd720-117">Your application will be subject to virtualization if either of the following conditions is true:</span></span>  
  
1.  <span data-ttu-id="dd720-118">您使用`-nowin32manifest`选项，并且不提供清单，在更高版本的生成步骤中或者在 Windows 资源 (.res) 文件通过使用`-win32resource`选项。</span><span class="sxs-lookup"><span data-stu-id="dd720-118">You use the `-nowin32manifest` option and you do not provide a manifest in a later build step or as part of a Windows Resource (.res) file by using the `-win32resource` option.</span></span>  
  
2.  <span data-ttu-id="dd720-119">提供的自定义清单未指定请求执行级别。</span><span class="sxs-lookup"><span data-stu-id="dd720-119">You provide a custom manifest that does not specify a requested execution level.</span></span>  
  
 <span data-ttu-id="dd720-120">Visual Studio 创建默认 .manifest 文件，并将它与可执行文件一起存储在“调试”和“发布”目录中。</span><span class="sxs-lookup"><span data-stu-id="dd720-120">Visual Studio creates a default .manifest file and stores it in the debug and release directories alongside the executable file.</span></span> <span data-ttu-id="dd720-121">您可以查看或编辑默认应用程序清单文件，方法是单击**查看 UAC 设置**上**应用程序**项目设计器中的选项卡。</span><span class="sxs-lookup"><span data-stu-id="dd720-121">You can view or edit the default app.manifest file by clicking **View UAC Settings** on the **Application** tab in the Project Designer.</span></span> <span data-ttu-id="dd720-122">有关详细信息，请参阅 [Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic)（应用程序页、项目设计器 (Visual Basic)。</span><span class="sxs-lookup"><span data-stu-id="dd720-122">For more information, see [Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic).</span></span>  
  
 <span data-ttu-id="dd720-123">您可以通过使用提供的应用程序清单作为自定义后期生成步骤或作为 Win32 资源文件的一部分`-nowin32manifest`选项。</span><span class="sxs-lookup"><span data-stu-id="dd720-123">You can provide the application manifest as a custom post-build step or as part of a Win32 resource file by using the `-nowin32manifest` option.</span></span> <span data-ttu-id="dd720-124">如果希望应用程序受到 Windows Vista 的文件或注册表虚拟化的影响，请使用该选项。</span><span class="sxs-lookup"><span data-stu-id="dd720-124">Use that same option if you want your application to be subject to file or registry virtualization on Windows Vista.</span></span> <span data-ttu-id="dd720-125">这将阻止编译器创建并在 PE 文件中嵌入默认清单。</span><span class="sxs-lookup"><span data-stu-id="dd720-125">This will prevent the compiler from creating and embedding a default manifest in the PE file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dd720-126">示例</span><span class="sxs-lookup"><span data-stu-id="dd720-126">Example</span></span>  
 <span data-ttu-id="dd720-127">下面的示例演示了 Visual Basic 编译器插入到 PE 默认清单。</span><span class="sxs-lookup"><span data-stu-id="dd720-127">The following example shows the default manifest that the Visual Basic compiler inserts into a PE.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dd720-128">编译器将插入到清单 XML 的标准应用程序名称 MyApplication.app。</span><span class="sxs-lookup"><span data-stu-id="dd720-128">The compiler inserts a standard application name MyApplication.app into the manifest XML.</span></span> <span data-ttu-id="dd720-129">这是一种使应用程序可以在 Windows Server 2003 Service Pack 3 上运行的解决方法。</span><span class="sxs-lookup"><span data-stu-id="dd720-129">This is a workaround to enable applications to run on Windows Server 2003 Service Pack 3.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="dd720-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="dd720-130">See Also</span></span>  
 [<span data-ttu-id="dd720-131">Visual Basic 命令行编译器</span><span class="sxs-lookup"><span data-stu-id="dd720-131">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="dd720-132">-nowin32manifest (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="dd720-132">-nowin32manifest (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/nowin32manifest.md)
