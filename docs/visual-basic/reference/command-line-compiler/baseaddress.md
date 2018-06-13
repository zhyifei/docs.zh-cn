---
title: -baseaddress
ms.date: 08/09/2018
f1_keywords:
- /baseaddress
- baseaddress
helpviewer_keywords:
- -baseaddress compiler option [Visual Basic]
- /baseaddress compiler option [Visual Basic]
- baseaddress compiler option [Visual Basic]
ms.assetid: c982bcf2-46e5-47a2-bc8f-a5cc32b7dc47
ms.openlocfilehash: 6331a55bb1d20b5804605db103dcfd2997e348d9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33650145"
---
# <a name="-baseaddress"></a><span data-ttu-id="c6b6d-102">-baseaddress</span><span class="sxs-lookup"><span data-stu-id="c6b6d-102">-baseaddress</span></span>
<span data-ttu-id="c6b6d-103">创建 DLL 时，请指定默认的基址。</span><span class="sxs-lookup"><span data-stu-id="c6b6d-103">Specifies a default base address when creating a DLL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6b6d-104">语法</span><span class="sxs-lookup"><span data-stu-id="c6b6d-104">Syntax</span></span>  
  
```  
-baseaddress:address  
```  
  
## <a name="arguments"></a><span data-ttu-id="c6b6d-105">自变量</span><span class="sxs-lookup"><span data-stu-id="c6b6d-105">Arguments</span></span>  
  
|<span data-ttu-id="c6b6d-106">术语</span><span class="sxs-lookup"><span data-stu-id="c6b6d-106">Term</span></span>|<span data-ttu-id="c6b6d-107">定义</span><span class="sxs-lookup"><span data-stu-id="c6b6d-107">Definition</span></span>|  
|---|---|  
|`address`|<span data-ttu-id="c6b6d-108">必须的。</span><span class="sxs-lookup"><span data-stu-id="c6b6d-108">Required.</span></span> <span data-ttu-id="c6b6d-109">DLL 的基址。</span><span class="sxs-lookup"><span data-stu-id="c6b6d-109">The base address for the DLL.</span></span> <span data-ttu-id="c6b6d-110">此地址必须指定为十六进制数。</span><span class="sxs-lookup"><span data-stu-id="c6b6d-110">This address must be specified as a hexadecimal number.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c6b6d-111">备注</span><span class="sxs-lookup"><span data-stu-id="c6b6d-111">Remarks</span></span>  
 <span data-ttu-id="c6b6d-112">设置 DLL 的默认基址[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="c6b6d-112">The default base address for a DLL is set by the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span></span>  
  
 <span data-ttu-id="c6b6d-113">请注意，此地址中的较低序位字被舍入。</span><span class="sxs-lookup"><span data-stu-id="c6b6d-113">Be aware that the lower-order word in this address is rounded.</span></span> <span data-ttu-id="c6b6d-114">例如，如果指定 0x11110001，它是舍入为 0x11110000。</span><span class="sxs-lookup"><span data-stu-id="c6b6d-114">For example, if you specify 0x11110001, it is rounded to 0x11110000.</span></span>  
  
 <span data-ttu-id="c6b6d-115">若要完成 DLL 的签名的过程，使用`–R`的强命名工具 (Sn.exe) 的选项。</span><span class="sxs-lookup"><span data-stu-id="c6b6d-115">To complete the signing process for a DLL, use the `–R` option of the Strong Naming tool (Sn.exe).</span></span>  
  
 <span data-ttu-id="c6b6d-116">如果目标不是 DLL，则忽略此选项。</span><span class="sxs-lookup"><span data-stu-id="c6b6d-116">This option is ignored if the target is not a DLL.</span></span>  
  
|<span data-ttu-id="c6b6d-117">在 Visual Studio IDE 中设置-baseaddress</span><span class="sxs-lookup"><span data-stu-id="c6b6d-117">To set -baseaddress in the Visual Studio IDE</span></span>|  
|---|  
|<span data-ttu-id="c6b6d-118">1.在 **“解决方案资源管理器”** 中选择一个项目。</span><span class="sxs-lookup"><span data-stu-id="c6b6d-118">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="c6b6d-119">在“项目”菜单上，单击“属性”。</span><span class="sxs-lookup"><span data-stu-id="c6b6d-119">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="c6b6d-120">2.单击“编译”选项卡。</span><span class="sxs-lookup"><span data-stu-id="c6b6d-120">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="c6b6d-121">3.单击 **“高级”**。</span><span class="sxs-lookup"><span data-stu-id="c6b6d-121">3.  Click **Advanced**.</span></span><br /><span data-ttu-id="c6b6d-122">4.修改中的值**DLL 的基址：** 框。</span><span class="sxs-lookup"><span data-stu-id="c6b6d-122">4.  Modify the value in the **DLL base address:** box.</span></span> <span data-ttu-id="c6b6d-123">**注意：** **DLL 的基址：** 框是只读的除非目标是一个 DLL。</span><span class="sxs-lookup"><span data-stu-id="c6b6d-123">**Note:**      The **DLL base address:** box is read-only unless the target is a DLL.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c6b6d-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="c6b6d-124">See Also</span></span>  
 [<span data-ttu-id="c6b6d-125">Visual Basic 命令行编译器</span><span class="sxs-lookup"><span data-stu-id="c6b6d-125">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="c6b6d-126">-目标 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c6b6d-126">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)  
 [<span data-ttu-id="c6b6d-127">示例编译命令行</span><span class="sxs-lookup"><span data-stu-id="c6b6d-127">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 <span data-ttu-id="c6b6d-128">[Sn.exe （强名称工具）][Sn.exe （强名称工具）](../../../framework/tools/sn-exe-strong-name-tool.md))</span><span class="sxs-lookup"><span data-stu-id="c6b6d-128">[Sn.exe (Strong Name Tool)][Sn.exe (Strong Name Tool)](../../../framework/tools/sn-exe-strong-name-tool.md))</span></span>
