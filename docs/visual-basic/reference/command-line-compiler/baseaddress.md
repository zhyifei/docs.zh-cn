---
title: /baseaddress
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- /baseaddress
- baseaddress
helpviewer_keywords:
- -baseaddress compiler option [Visual Basic]
- /baseaddress compiler option [Visual Basic]
- baseaddress compiler option [Visual Basic]
ms.assetid: c982bcf2-46e5-47a2-bc8f-a5cc32b7dc47
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 8be88bf4834ca58b1fe708eb1ef7188c583fef0f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="baseaddress"></a><span data-ttu-id="d8e1b-102">/baseaddress</span><span class="sxs-lookup"><span data-stu-id="d8e1b-102">/baseaddress</span></span>
<span data-ttu-id="d8e1b-103">创建 DLL 时，请指定默认的基址。</span><span class="sxs-lookup"><span data-stu-id="d8e1b-103">Specifies a default base address when creating a DLL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d8e1b-104">语法</span><span class="sxs-lookup"><span data-stu-id="d8e1b-104">Syntax</span></span>  
  
```  
/baseaddress:address  
```  
  
## <a name="arguments"></a><span data-ttu-id="d8e1b-105">参数</span><span class="sxs-lookup"><span data-stu-id="d8e1b-105">Arguments</span></span>  
  
|<span data-ttu-id="d8e1b-106">术语</span><span class="sxs-lookup"><span data-stu-id="d8e1b-106">Term</span></span>|<span data-ttu-id="d8e1b-107">定义</span><span class="sxs-lookup"><span data-stu-id="d8e1b-107">Definition</span></span>|  
|---|---|  
|`address`|<span data-ttu-id="d8e1b-108">必需。</span><span class="sxs-lookup"><span data-stu-id="d8e1b-108">Required.</span></span> <span data-ttu-id="d8e1b-109">DLL 的基址。</span><span class="sxs-lookup"><span data-stu-id="d8e1b-109">The base address for the DLL.</span></span> <span data-ttu-id="d8e1b-110">此地址必须指定为十六进制数。</span><span class="sxs-lookup"><span data-stu-id="d8e1b-110">This address must be specified as a hexadecimal number.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d8e1b-111">备注</span><span class="sxs-lookup"><span data-stu-id="d8e1b-111">Remarks</span></span>  
 <span data-ttu-id="d8e1b-112">设置 DLL 的默认基址[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="d8e1b-112">The default base address for a DLL is set by the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span></span>  
  
 <span data-ttu-id="d8e1b-113">请注意，此地址中的较低序位字被舍入。</span><span class="sxs-lookup"><span data-stu-id="d8e1b-113">Be aware that the lower-order word in this address is rounded.</span></span> <span data-ttu-id="d8e1b-114">例如，如果指定 0x11110001，它是舍入为 0x11110000。</span><span class="sxs-lookup"><span data-stu-id="d8e1b-114">For example, if you specify 0x11110001, it is rounded to 0x11110000.</span></span>  
  
 <span data-ttu-id="d8e1b-115">若要完成 DLL 的签名的过程，使用`–R`的强命名工具 (Sn.exe) 的选项。</span><span class="sxs-lookup"><span data-stu-id="d8e1b-115">To complete the signing process for a DLL, use the `–R` option of the Strong Naming tool (Sn.exe).</span></span>  
  
 <span data-ttu-id="d8e1b-116">如果目标不是 DLL，则忽略此选项。</span><span class="sxs-lookup"><span data-stu-id="d8e1b-116">This option is ignored if the target is not a DLL.</span></span>  
  
|<span data-ttu-id="d8e1b-117">在 Visual Studio IDE 中设置 /baseaddress</span><span class="sxs-lookup"><span data-stu-id="d8e1b-117">To set /baseaddress in the Visual Studio IDE</span></span>|  
|---|  
|<span data-ttu-id="d8e1b-118">1.在 “解决方案资源管理器”中选择一个项目。</span><span class="sxs-lookup"><span data-stu-id="d8e1b-118">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="d8e1b-119">在“项目”菜单上，单击“属性”。</span><span class="sxs-lookup"><span data-stu-id="d8e1b-119">On the **Project** menu, click **Properties**.</span></span> <span data-ttu-id="d8e1b-120">有关详细信息，请参阅[项目设计器简介](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7)。</span><span class="sxs-lookup"><span data-stu-id="d8e1b-120">For more information, see [Introduction to the Project Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span></span><br /><span data-ttu-id="d8e1b-121">2.单击“编译”选项卡。</span><span class="sxs-lookup"><span data-stu-id="d8e1b-121">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="d8e1b-122">3.单击 **“高级”**。</span><span class="sxs-lookup"><span data-stu-id="d8e1b-122">3.  Click **Advanced**.</span></span><br /><span data-ttu-id="d8e1b-123">4.修改中的值**DLL 的基址：**框。</span><span class="sxs-lookup"><span data-stu-id="d8e1b-123">4.  Modify the value in the **DLL base address:** box.</span></span> <span data-ttu-id="d8e1b-124">**注意：** **DLL 的基址：**框是只读的除非目标是一个 DLL。</span><span class="sxs-lookup"><span data-stu-id="d8e1b-124">**Note:**      The **DLL base address:** box is read-only unless the target is a DLL.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d8e1b-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d8e1b-125">See Also</span></span>  
 [<span data-ttu-id="d8e1b-126">Visual Basic 命令行编译器</span><span class="sxs-lookup"><span data-stu-id="d8e1b-126">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="d8e1b-127">/target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d8e1b-127">/target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)  
 [<span data-ttu-id="d8e1b-128">示例编译命令行</span><span class="sxs-lookup"><span data-stu-id="d8e1b-128">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [<span data-ttu-id="d8e1b-129">Sn.exe（强名称工具）</span><span class="sxs-lookup"><span data-stu-id="d8e1b-129">Sn.exe (Strong Name Tool)</span></span>](https://msdn.microsoft.com/library/k5b5tt23)
