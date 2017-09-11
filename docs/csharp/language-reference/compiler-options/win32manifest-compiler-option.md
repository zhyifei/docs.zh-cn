---
title: "-win32manifest（C# 编译器选项）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /win32manifest
dev_langs:
- CSharp
helpviewer_keywords:
- /win32manifest compiler option [C#]
- win32manifest compiler option [C#]
- -win32manifest compiler option [C#]
ms.assetid: 9460ea1b-6c9f-44b8-8f73-301b30a01de1
caps.latest.revision: 13
author: BillWagner
ms.author: wiwagn
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 938317fdf0c56469b85b1231a47f83e9c2a7d0f2
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="win32manifest-c-compiler-options"></a><span data-ttu-id="0510e-102">/win32manifest（C# 编译器选项）</span><span class="sxs-lookup"><span data-stu-id="0510e-102">/win32manifest (C# Compiler Options)</span></span>
<span data-ttu-id="0510e-103">使用 **/win32manifest** 选项可以指定要嵌入到项目的可迁移可执行 (PE) 文件中的用户定义的 Win32 应用程序清单文件。</span><span class="sxs-lookup"><span data-stu-id="0510e-103">Use the **/win32manifest** option to specify a user-defined Win32 application manifest file to be embedded into a project's portable executable (PE) file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0510e-104">语法</span><span class="sxs-lookup"><span data-stu-id="0510e-104">Syntax</span></span>  
  
```console  
/win32manifest: filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="0510e-105">参数</span><span class="sxs-lookup"><span data-stu-id="0510e-105">Arguments</span></span>  
 `filename`  
 <span data-ttu-id="0510e-106">自定义清单文件的名称和位置。</span><span class="sxs-lookup"><span data-stu-id="0510e-106">The name and location of the custom manifest file.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0510e-107">备注</span><span class="sxs-lookup"><span data-stu-id="0510e-107">Remarks</span></span>  
 <span data-ttu-id="0510e-108">默认情况下，[!INCLUDE[csharp_current_short](~/includes/csharp-current-short-md.md)] 编译器嵌入指定“asInvoker”的请求执行级别的应用程序清单。</span><span class="sxs-lookup"><span data-stu-id="0510e-108">By default, the [!INCLUDE[csharp_current_short](~/includes/csharp-current-short-md.md)] compiler embeds an application manifest that specifies a requested execution level of "asInvoker."</span></span> <span data-ttu-id="0510e-109">它在生成该可执行文件的同一文件夹中创建清单，如果使用 Visual Studio，该文件夹通常为 bin\Debug 或 bin\Release。</span><span class="sxs-lookup"><span data-stu-id="0510e-109">It creates the manifest in the same folder in which the executable is built, typically the bin\Debug or bin\Release folder when you use Visual Studio.</span></span> <span data-ttu-id="0510e-110">如果要提供自定义清单（例如，指定“highestAvailable”或“requireAdministrator”的请求执行级别的清单），请使用此选项指定文件名。</span><span class="sxs-lookup"><span data-stu-id="0510e-110">If you want to supply a custom manifest, for example to specify a requested execution level of "highestAvailable" or "requireAdministrator," use this option to specify the name of the file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0510e-111">此选项和 [/win32res（C# 编译器选项）](../../../csharp/language-reference/compiler-options/win32res-compiler-option.md)选项是互斥的。</span><span class="sxs-lookup"><span data-stu-id="0510e-111">This option and the [/win32res (C# Compiler Options)](../../../csharp/language-reference/compiler-options/win32res-compiler-option.md) option are mutually exclusive.</span></span> <span data-ttu-id="0510e-112">如果尝试在同一命令行中同时使用这两个选项，将收到一个生成错误。</span><span class="sxs-lookup"><span data-stu-id="0510e-112">If you try to use both options in the same command line you will get a build error.</span></span>  
  
 <span data-ttu-id="0510e-113">如果应用程序没有用于指定请求执行级别的应用程序清单，将受到 Windows Vista 的用户帐户控制功能下的文件/注册表虚拟化的影响。</span><span class="sxs-lookup"><span data-stu-id="0510e-113">An application that has no application manifest that specifies a requested execution level will be subject to file/registry virtualization under the User Account Control feature in Windows Vista.</span></span> <span data-ttu-id="0510e-114">有关虚拟化的详细信息，请参阅 [Windows Vista Developer Story：针对用户帐户控制的 Windows Vista 应用程序开发要求](http://go.microsoft.com/fwlink/?LinkId=95452)。</span><span class="sxs-lookup"><span data-stu-id="0510e-114">For more information about virtualization, see [The Windows Vista Developer Story: Windows Vista Application Development Requirements for User Account Control (UAC)](http://go.microsoft.com/fwlink/?LinkId=95452).</span></span>  
  
 <span data-ttu-id="0510e-115">如果满足下列任一条件，则应用程序会受到虚拟化的影响：</span><span class="sxs-lookup"><span data-stu-id="0510e-115">Your application will be subject to virtualization if either of these conditions is true:</span></span>  
  
-   <span data-ttu-id="0510e-116">使用 **/nowin32manifest** 选项，并且在随后的生成步骤中未提供清单，或者没有通过使用 **/win32res** 选项将其包含在 Windows 资源 (.res) 文件中。</span><span class="sxs-lookup"><span data-stu-id="0510e-116">You use the **/nowin32manifest** option and you do not provide a manifest in a later build step or as part of a Windows Resource (.res) file by using the **/win32res** option.</span></span>  
  
-   <span data-ttu-id="0510e-117">提供的自定义清单未指定请求执行级别。</span><span class="sxs-lookup"><span data-stu-id="0510e-117">You provide a custom manifest that does not specify a requested execution level.</span></span>  
  
 [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)]<span data-ttu-id="0510e-118"> 创建默认的 .manifest 文件，并将该文件与可执行文件一起存储在 debug 和 release 目录中。</span><span class="sxs-lookup"><span data-stu-id="0510e-118"> creates a default .manifest file and stores it in the debug and release directories alongside the executable file.</span></span> <span data-ttu-id="0510e-119">可以用任意文本编辑器创建一个清单，然后将该文件添加到项目中，从而添加自定义清单。</span><span class="sxs-lookup"><span data-stu-id="0510e-119">You can add a custom manifest by creating one in any text editor and then adding the file to the project.</span></span> <span data-ttu-id="0510e-120">或者，也可以右键单击“解决方案资源管理器”中的“项目”图标，单击“添加新项”，然后单击“应用程序清单文件”。</span><span class="sxs-lookup"><span data-stu-id="0510e-120">Alternatively, you can right-click the **Project** icon in **Solution Explorer**, click **Add New Item**, and then click **Application Manifest File**.</span></span> <span data-ttu-id="0510e-121">添加完新的或现有清单文件后，该文件将显示在“清单”下拉列表中。</span><span class="sxs-lookup"><span data-stu-id="0510e-121">After you have added your new or existing manifest file, it will appear in the **Manifest** drop down list.</span></span> <span data-ttu-id="0510e-122">有关详细信息，请参阅[“项目设计器”->“应用程序”页 (C#)](/visualstudio/ide/reference/application-page-project-designer-csharp)。</span><span class="sxs-lookup"><span data-stu-id="0510e-122">For more information, see [Application Page, Project Designer (C#)](/visualstudio/ide/reference/application-page-project-designer-csharp).</span></span>  
  
 <span data-ttu-id="0510e-123">提供应用程序清单的操作，可以作为自定义后期生成步骤，也可以通过使用 [/nowin32manifest（C# 编译器选项）](../../../csharp/language-reference/compiler-options/nowin32manifest-compiler-option.md)选项作为 Win32 资源文件的组成部分。</span><span class="sxs-lookup"><span data-stu-id="0510e-123">You can provide the application manifest as a custom post-build step or as part of a Win32 resource file by using the [/nowin32manifest (C# Compiler Options)](../../../csharp/language-reference/compiler-options/nowin32manifest-compiler-option.md) option.</span></span> <span data-ttu-id="0510e-124">如果希望应用程序受到 Windows Vista 的文件或注册表虚拟化的影响，请使用该选项。</span><span class="sxs-lookup"><span data-stu-id="0510e-124">Use that same option if you want your application to be subject to file or registry virtualization on Windows Vista.</span></span> <span data-ttu-id="0510e-125">这将阻止编译器在可迁移可执行 (PE) 文件中创建和嵌入默认清单。</span><span class="sxs-lookup"><span data-stu-id="0510e-125">This will prevent the compiler from creating and embedding a default manifest in the portable executable (PE) file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0510e-126">示例</span><span class="sxs-lookup"><span data-stu-id="0510e-126">Example</span></span>  
 <span data-ttu-id="0510e-127">下例演示了 Visual C# 编译器插入到 PE 中的默认清单。</span><span class="sxs-lookup"><span data-stu-id="0510e-127">The following example shows the default manifest that the Visual C# compiler inserts into a PE.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0510e-128">编译器将一个标准应用程序名称“MyApplication.app”插入到 xml 中。</span><span class="sxs-lookup"><span data-stu-id="0510e-128">The compiler inserts a standard application name " MyApplication.app " into the xml.</span></span> <span data-ttu-id="0510e-129">这是一种使应用程序可以在 Windows Server 2003 Service Pack 3 上运行的解决方法。</span><span class="sxs-lookup"><span data-stu-id="0510e-129">This is a workaround to enable applications to run on Windows Server 2003 Service Pack 3.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="0510e-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="0510e-130">See Also</span></span>  
 <span data-ttu-id="0510e-131">[（C# 编译器选项）](../../../csharp/language-reference/compiler-options/index.md) </span><span class="sxs-lookup"><span data-stu-id="0510e-131">[C# Compiler Options](../../../csharp/language-reference/compiler-options/index.md) </span></span>  
 <span data-ttu-id="0510e-132">[/nowin32manifest（C# 编译器选项）](../../../csharp/language-reference/compiler-options/nowin32manifest-compiler-option.md) </span><span class="sxs-lookup"><span data-stu-id="0510e-132">[/nowin32manifest (C# Compiler Options)](../../../csharp/language-reference/compiler-options/nowin32manifest-compiler-option.md) </span></span>  
 [<span data-ttu-id="0510e-133">管理项目和解决方案属性</span><span class="sxs-lookup"><span data-stu-id="0510e-133">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)

