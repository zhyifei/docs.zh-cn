---
title: /win32icon
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- win32icon compiler option [Visual Basic]
- -win32icon compiler option [Visual Basic]
- /win32icon compiler option [Visual Basic]
ms.assetid: aecaab01-9353-46c5-941c-6edabd4eff92
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 65149c617220966bc3bb6897d757a71cd60167d6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="win32icon"></a><span data-ttu-id="e943c-102">/win32icon</span><span class="sxs-lookup"><span data-stu-id="e943c-102">/win32icon</span></span>
<span data-ttu-id="e943c-103">将.ico 文件插入到输出文件中。</span><span class="sxs-lookup"><span data-stu-id="e943c-103">Inserts an .ico file in the output file.</span></span> <span data-ttu-id="e943c-104">此.ico 文件表示中的输出文件**文件资源管理器**。</span><span class="sxs-lookup"><span data-stu-id="e943c-104">This .ico file represents the output file in **File Explorer**.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e943c-105">语法</span><span class="sxs-lookup"><span data-stu-id="e943c-105">Syntax</span></span>  
  
```  
/win32icon:filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="e943c-106">参数</span><span class="sxs-lookup"><span data-stu-id="e943c-106">Arguments</span></span>  
  
|<span data-ttu-id="e943c-107">术语</span><span class="sxs-lookup"><span data-stu-id="e943c-107">Term</span></span>|<span data-ttu-id="e943c-108">定义</span><span class="sxs-lookup"><span data-stu-id="e943c-108">Definition</span></span>|  
|---|---|  
|`filename`|<span data-ttu-id="e943c-109">要添加到输出文件的.ico 文件。</span><span class="sxs-lookup"><span data-stu-id="e943c-109">The .ico file to add to your output file.</span></span> <span data-ttu-id="e943c-110">将文件名括在双引号 ("") 如果它包含空格。</span><span class="sxs-lookup"><span data-stu-id="e943c-110">Enclose the file name in quotation marks (" ") if it contains a space.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e943c-111">备注</span><span class="sxs-lookup"><span data-stu-id="e943c-111">Remarks</span></span>  
 <span data-ttu-id="e943c-112">你可以使用 Microsoft Windows 资源编译器 (RC) 创建.ico 文件。</span><span class="sxs-lookup"><span data-stu-id="e943c-112">You can create an .ico file with the Microsoft Windows Resource Compiler (RC).</span></span> <span data-ttu-id="e943c-113">编译 Visual c + + 程序; 时会调用资源编译器.ico 文件是从.rc 文件创建的。</span><span class="sxs-lookup"><span data-stu-id="e943c-113">The resource compiler is invoked when you compile a Visual C++ program; an .ico file is created from the .rc file.</span></span> <span data-ttu-id="e943c-114">`/win32icon`和`/win32resource`选项互斥。</span><span class="sxs-lookup"><span data-stu-id="e943c-114">The `/win32icon` and `/win32resource` options are mutually exclusive.</span></span>  
  
 <span data-ttu-id="e943c-115">请参阅[/linkresource (Visual Basic 中)](../../../visual-basic/reference/command-line-compiler/linkresource.md)引用[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]资源文件，或[/resource (Visual Basic 中)](../../../visual-basic/reference/command-line-compiler/resource.md)附加[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]资源文件。</span><span class="sxs-lookup"><span data-stu-id="e943c-115">See [/linkresource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/linkresource.md) to reference a [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] resource file, or [/resource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/resource.md) to attach a [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] resource file.</span></span> <span data-ttu-id="e943c-116">请参阅[/win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md)导入.res 文件。</span><span class="sxs-lookup"><span data-stu-id="e943c-116">See [/win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md) to import a .res file.</span></span>  
  
|<span data-ttu-id="e943c-117">在 Visual Studio IDE 中设置 /win32icon</span><span class="sxs-lookup"><span data-stu-id="e943c-117">To set /win32icon in the Visual Studio IDE</span></span>|  
|---|  
|<span data-ttu-id="e943c-118">1.在 “解决方案资源管理器”中选择一个项目。</span><span class="sxs-lookup"><span data-stu-id="e943c-118">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="e943c-119">在“项目”菜单上，单击“属性”。</span><span class="sxs-lookup"><span data-stu-id="e943c-119">On the **Project** menu, click **Properties**.</span></span> <span data-ttu-id="e943c-120">有关详细信息，请参阅[项目设计器简介](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7)。</span><span class="sxs-lookup"><span data-stu-id="e943c-120">For more information, see [Introduction to the Project Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span></span><br /><span data-ttu-id="e943c-121">2.单击“应用程序”  选项卡。</span><span class="sxs-lookup"><span data-stu-id="e943c-121">2.  Click the **Application** tab.</span></span><br /><span data-ttu-id="e943c-122">3.修改中的值**图标**框。</span><span class="sxs-lookup"><span data-stu-id="e943c-122">3.  Modify the value in the **Icon** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="e943c-123">示例</span><span class="sxs-lookup"><span data-stu-id="e943c-123">Example</span></span>  
 <span data-ttu-id="e943c-124">下面的代码编译`In.vb`和将.ico 文件，附加`Rf.ico`。</span><span class="sxs-lookup"><span data-stu-id="e943c-124">The following code compiles `In.vb` and attaches an .ico file, `Rf.ico`.</span></span>  
  
```  
vbc /win32icon:rf.ico in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="e943c-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e943c-125">See Also</span></span>  
 [<span data-ttu-id="e943c-126">Visual Basic 命令行编译器</span><span class="sxs-lookup"><span data-stu-id="e943c-126">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="e943c-127">示例编译命令行</span><span class="sxs-lookup"><span data-stu-id="e943c-127">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
