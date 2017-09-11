---
title: "/baseaddress |Microsoft 文档"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- /baseaddress
- baseaddress
dev_langs:
- VB
helpviewer_keywords:
- -baseaddress compiler option [Visual Basic]
- /baseaddress compiler option [Visual Basic]
- baseaddress compiler option [Visual Basic]
ms.assetid: c982bcf2-46e5-47a2-bc8f-a5cc32b7dc47
caps.latest.revision: 16
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
ms.openlocfilehash: 5687f119a57e0e54eca4df8f91fdf5e8b2775f82
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="baseaddress"></a><span data-ttu-id="77277-102">/baseaddress</span><span class="sxs-lookup"><span data-stu-id="77277-102">/baseaddress</span></span>
<span data-ttu-id="77277-103">指定默认的基址时创建 DLL。</span><span class="sxs-lookup"><span data-stu-id="77277-103">Specifies a default base address when creating a DLL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="77277-104">语法</span><span class="sxs-lookup"><span data-stu-id="77277-104">Syntax</span></span>  
  
```  
/baseaddress:address  
```  
  
## <a name="arguments"></a><span data-ttu-id="77277-105">参数</span><span class="sxs-lookup"><span data-stu-id="77277-105">Arguments</span></span>  
  
|<span data-ttu-id="77277-106">术语</span><span class="sxs-lookup"><span data-stu-id="77277-106">Term</span></span>|<span data-ttu-id="77277-107">定义</span><span class="sxs-lookup"><span data-stu-id="77277-107">Definition</span></span>|  
|---|---|  
|`address`|<span data-ttu-id="77277-108">必需。</span><span class="sxs-lookup"><span data-stu-id="77277-108">Required.</span></span> <span data-ttu-id="77277-109">此 DLL 的的基址。</span><span class="sxs-lookup"><span data-stu-id="77277-109">The base address for the DLL.</span></span> <span data-ttu-id="77277-110">必须将此地址指定为十六进制数。</span><span class="sxs-lookup"><span data-stu-id="77277-110">This address must be specified as a hexadecimal number.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="77277-111">备注</span><span class="sxs-lookup"><span data-stu-id="77277-111">Remarks</span></span>  
 <span data-ttu-id="77277-112">DLL 的默认基址将由[!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)]。</span><span class="sxs-lookup"><span data-stu-id="77277-112">The default base address for a DLL is set by the [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)].</span></span>  
  
 <span data-ttu-id="77277-113">请注意，此地址中的较低序位字被舍入。</span><span class="sxs-lookup"><span data-stu-id="77277-113">Be aware that the lower-order word in this address is rounded.</span></span> <span data-ttu-id="77277-114">例如，如果指定 0x11110001，它是舍入为 0x11110000。</span><span class="sxs-lookup"><span data-stu-id="77277-114">For example, if you specify 0x11110001, it is rounded to 0x11110000.</span></span>  
  
 <span data-ttu-id="77277-115">若要完成签名过程的 DLL，使用`–R`强命名工具 (Sn.exe) 的选项。</span><span class="sxs-lookup"><span data-stu-id="77277-115">To complete the signing process for a DLL, use the `–R` option of the Strong Naming tool (Sn.exe).</span></span>  
  
 <span data-ttu-id="77277-116">如果目标不是 DLL，则忽略此选项。</span><span class="sxs-lookup"><span data-stu-id="77277-116">This option is ignored if the target is not a DLL.</span></span>  
  
|<span data-ttu-id="77277-117">在 Visual Studio IDE 中设置 /baseaddress</span><span class="sxs-lookup"><span data-stu-id="77277-117">To set /baseaddress in the Visual Studio IDE</span></span>|  
|---|  
|<span data-ttu-id="77277-118">1.在 **“解决方案资源管理器”**中选择一个项目。</span><span class="sxs-lookup"><span data-stu-id="77277-118">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="77277-119">在**项目**菜单上，单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="77277-119">On the **Project** menu, click **Properties**.</span></span> <span data-ttu-id="77277-120">有关详细信息，请参阅[项目设计器简介](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7)。</span><span class="sxs-lookup"><span data-stu-id="77277-120">For more information, see [Introduction to the Project Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span></span><br /><span data-ttu-id="77277-121">2.单击“编译”****选项卡。</span><span class="sxs-lookup"><span data-stu-id="77277-121">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="77277-122">3.单击 **“高级”**。</span><span class="sxs-lookup"><span data-stu-id="77277-122">3.  Click **Advanced**.</span></span><br /><span data-ttu-id="77277-123">4.在修改此值**DLL 基址︰**框。</span><span class="sxs-lookup"><span data-stu-id="77277-123">4.  Modify the value in the **DLL base address:** box.</span></span> <span data-ttu-id="77277-124">**注意︰** **DLL 基址︰**框是只读的除非目标是一个 DLL。</span><span class="sxs-lookup"><span data-stu-id="77277-124">**Note:**      The **DLL base address:** box is read-only unless the target is a DLL.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="77277-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="77277-125">See Also</span></span>  
 <span data-ttu-id="77277-126">[Visual Basic 命令行编译器](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="77277-126">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="77277-127"> [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md) </span><span class="sxs-lookup"><span data-stu-id="77277-127"> [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md) </span></span>  
<span data-ttu-id="77277-128"> [示例编译命令行](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span><span class="sxs-lookup"><span data-stu-id="77277-128"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span></span>  
<span data-ttu-id="77277-129"> [Sn.exe （强名称工具）](https://msdn.microsoft.com/library/k5b5tt23)</span><span class="sxs-lookup"><span data-stu-id="77277-129"> [Sn.exe (Strong Name Tool)](https://msdn.microsoft.com/library/k5b5tt23)</span></span>
