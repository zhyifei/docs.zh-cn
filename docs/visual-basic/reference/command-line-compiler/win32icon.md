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
ms.openlocfilehash: 4fc5210d2dcf30d9c4603b67b890c78510af1338
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="win32icon"></a><span data-ttu-id="1cc8f-102">/win32icon</span><span class="sxs-lookup"><span data-stu-id="1cc8f-102">/win32icon</span></span>
<span data-ttu-id="1cc8f-103">将.ico 文件插入到输出文件中。</span><span class="sxs-lookup"><span data-stu-id="1cc8f-103">Inserts an .ico file in the output file.</span></span> <span data-ttu-id="1cc8f-104">此.ico 文件表示中的输出文件**文件资源管理器**。</span><span class="sxs-lookup"><span data-stu-id="1cc8f-104">This .ico file represents the output file in **File Explorer**.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1cc8f-105">语法</span><span class="sxs-lookup"><span data-stu-id="1cc8f-105">Syntax</span></span>  
  
```  
/win32icon:filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="1cc8f-106">自变量</span><span class="sxs-lookup"><span data-stu-id="1cc8f-106">Arguments</span></span>  
  
|<span data-ttu-id="1cc8f-107">术语</span><span class="sxs-lookup"><span data-stu-id="1cc8f-107">Term</span></span>|<span data-ttu-id="1cc8f-108">定义</span><span class="sxs-lookup"><span data-stu-id="1cc8f-108">Definition</span></span>|  
|---|---|  
|`filename`|<span data-ttu-id="1cc8f-109">要添加到输出文件的.ico 文件。</span><span class="sxs-lookup"><span data-stu-id="1cc8f-109">The .ico file to add to your output file.</span></span> <span data-ttu-id="1cc8f-110">将文件名括在双引号 ("") 如果它包含空格。</span><span class="sxs-lookup"><span data-stu-id="1cc8f-110">Enclose the file name in quotation marks (" ") if it contains a space.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1cc8f-111">备注</span><span class="sxs-lookup"><span data-stu-id="1cc8f-111">Remarks</span></span>  
 <span data-ttu-id="1cc8f-112">你可以使用 Microsoft Windows 资源编译器 (RC) 创建.ico 文件。</span><span class="sxs-lookup"><span data-stu-id="1cc8f-112">You can create an .ico file with the Microsoft Windows Resource Compiler (RC).</span></span> <span data-ttu-id="1cc8f-113">编译 Visual c + + 程序; 时会调用资源编译器.ico 文件是从.rc 文件创建的。</span><span class="sxs-lookup"><span data-stu-id="1cc8f-113">The resource compiler is invoked when you compile a Visual C++ program; an .ico file is created from the .rc file.</span></span> <span data-ttu-id="1cc8f-114">`/win32icon`和`/win32resource`选项互斥。</span><span class="sxs-lookup"><span data-stu-id="1cc8f-114">The `/win32icon` and `/win32resource` options are mutually exclusive.</span></span>  
  
 <span data-ttu-id="1cc8f-115">请参阅[/linkresource (Visual Basic 中)](../../../visual-basic/reference/command-line-compiler/linkresource.md)引用[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]资源文件，或[/resource (Visual Basic 中)](../../../visual-basic/reference/command-line-compiler/resource.md)附加[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]资源文件。</span><span class="sxs-lookup"><span data-stu-id="1cc8f-115">See [/linkresource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/linkresource.md) to reference a [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] resource file, or [/resource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/resource.md) to attach a [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] resource file.</span></span> <span data-ttu-id="1cc8f-116">请参阅[/win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md)导入.res 文件。</span><span class="sxs-lookup"><span data-stu-id="1cc8f-116">See [/win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md) to import a .res file.</span></span>  
  
|<span data-ttu-id="1cc8f-117">在 Visual Studio IDE 中设置 /win32icon</span><span class="sxs-lookup"><span data-stu-id="1cc8f-117">To set /win32icon in the Visual Studio IDE</span></span>|  
|---|  
|<span data-ttu-id="1cc8f-118">1.在 **“解决方案资源管理器”**中选择一个项目。</span><span class="sxs-lookup"><span data-stu-id="1cc8f-118">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="1cc8f-119">在“项目”菜单上，单击“属性”。</span><span class="sxs-lookup"><span data-stu-id="1cc8f-119">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="1cc8f-120">2.单击“应用程序”  选项卡。</span><span class="sxs-lookup"><span data-stu-id="1cc8f-120">2.  Click the **Application** tab.</span></span><br /><span data-ttu-id="1cc8f-121">3.修改中的值**图标**框。</span><span class="sxs-lookup"><span data-stu-id="1cc8f-121">3.  Modify the value in the **Icon** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="1cc8f-122">示例</span><span class="sxs-lookup"><span data-stu-id="1cc8f-122">Example</span></span>  
 <span data-ttu-id="1cc8f-123">下面的代码编译`In.vb`和将.ico 文件，附加`Rf.ico`。</span><span class="sxs-lookup"><span data-stu-id="1cc8f-123">The following code compiles `In.vb` and attaches an .ico file, `Rf.ico`.</span></span>  
  
```  
vbc /win32icon:rf.ico in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="1cc8f-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="1cc8f-124">See Also</span></span>  
 [<span data-ttu-id="1cc8f-125">Visual Basic 命令行编译器</span><span class="sxs-lookup"><span data-stu-id="1cc8f-125">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="1cc8f-126">示例编译命令行</span><span class="sxs-lookup"><span data-stu-id="1cc8f-126">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
