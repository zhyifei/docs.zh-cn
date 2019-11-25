---
title: -out
ms.date: 07/20/2015
helpviewer_keywords:
- /out compiler option [Visual Basic]
- -out compiler option [Visual Basic]
- out compiler option [Visual Basic]
ms.assetid: 9f148c15-0909-4cb8-a2db-777f8a8b45ae
ms.openlocfilehash: 67366e13e4dceea4772d0730222413cb25b4e8b7
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352386"
---
# <a name="-out-visual-basic"></a><span data-ttu-id="4ec86-102">-out (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4ec86-102">-out (Visual Basic)</span></span>
<span data-ttu-id="4ec86-103">指定输出文件的名称。</span><span class="sxs-lookup"><span data-stu-id="4ec86-103">Specifies the name of the output file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4ec86-104">语法</span><span class="sxs-lookup"><span data-stu-id="4ec86-104">Syntax</span></span>  
  
```console  
-out:filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="4ec86-105">自变量</span><span class="sxs-lookup"><span data-stu-id="4ec86-105">Arguments</span></span>  
  
|<span data-ttu-id="4ec86-106">术语</span><span class="sxs-lookup"><span data-stu-id="4ec86-106">Term</span></span>|<span data-ttu-id="4ec86-107">定义</span><span class="sxs-lookup"><span data-stu-id="4ec86-107">Definition</span></span>|  
|---|---|  
|`filename`|<span data-ttu-id="4ec86-108">必须的。</span><span class="sxs-lookup"><span data-stu-id="4ec86-108">Required.</span></span> <span data-ttu-id="4ec86-109">The name of the output file the compiler creates.</span><span class="sxs-lookup"><span data-stu-id="4ec86-109">The name of the output file the compiler creates.</span></span> <span data-ttu-id="4ec86-110">If the file name contains a space, enclose the name in quotation marks (" ").</span><span class="sxs-lookup"><span data-stu-id="4ec86-110">If the file name contains a space, enclose the name in quotation marks (" ").</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4ec86-111">备注</span><span class="sxs-lookup"><span data-stu-id="4ec86-111">Remarks</span></span>  
 <span data-ttu-id="4ec86-112">Specify the full name and extension of the file to create.</span><span class="sxs-lookup"><span data-stu-id="4ec86-112">Specify the full name and extension of the file to create.</span></span> <span data-ttu-id="4ec86-113">If you do not, the .exe file takes its name from the source-code file containing the `Sub Main` procedure, and the .dll file takes its name from the first source-code file.</span><span class="sxs-lookup"><span data-stu-id="4ec86-113">If you do not, the .exe file takes its name from the source-code file containing the `Sub Main` procedure, and the .dll file takes its name from the first source-code file.</span></span>  
  
 <span data-ttu-id="4ec86-114">If you specify a file name without an .exe or .dll extension, the compiler automatically adds the extension for you, depending on the value specified for the `-target` compiler option.</span><span class="sxs-lookup"><span data-stu-id="4ec86-114">If you specify a file name without an .exe or .dll extension, the compiler automatically adds the extension for you, depending on the value specified for the `-target` compiler option.</span></span>  
  
|<span data-ttu-id="4ec86-115">To set -out in the Visual Studio integrated development environment</span><span class="sxs-lookup"><span data-stu-id="4ec86-115">To set -out in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="4ec86-116">1.  Have a project selected in **Solution Explorer**.</span><span class="sxs-lookup"><span data-stu-id="4ec86-116">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="4ec86-117">在“项目”菜单上，单击“属性”。</span><span class="sxs-lookup"><span data-stu-id="4ec86-117">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="4ec86-118">2.  Click the **Application** tab.</span><span class="sxs-lookup"><span data-stu-id="4ec86-118">2.  Click the **Application** tab.</span></span><br /><span data-ttu-id="4ec86-119">3.  Modify the value in the **Assembly Name** box.</span><span class="sxs-lookup"><span data-stu-id="4ec86-119">3.  Modify the value in the **Assembly Name** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="4ec86-120">示例</span><span class="sxs-lookup"><span data-stu-id="4ec86-120">Example</span></span>  
 <span data-ttu-id="4ec86-121">The following code compiles `T2.vb` and creates output file `T2.exe`.</span><span class="sxs-lookup"><span data-stu-id="4ec86-121">The following code compiles `T2.vb` and creates output file `T2.exe`.</span></span>  
  
```console
vbc t2.vb -out:t3.exe  
```  
  
## <a name="see-also"></a><span data-ttu-id="4ec86-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="4ec86-122">See also</span></span>

- [<span data-ttu-id="4ec86-123">Visual Basic 命令行编译器</span><span class="sxs-lookup"><span data-stu-id="4ec86-123">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="4ec86-124">-target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4ec86-124">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)
- [<span data-ttu-id="4ec86-125">示例编译命令行</span><span class="sxs-lookup"><span data-stu-id="4ec86-125">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
