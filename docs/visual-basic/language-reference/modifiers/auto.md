---
title: Auto (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Auto
helpviewer_keywords:
- Auto keyword [Visual Basic], external references
- Declare statement [Visual Basic], marshaling strings
- Auto keyword [Visual Basic]
- Auto keyword [Visual Basic], marshaling strings
ms.assetid: bf79ba95-a62c-48a5-916f-0ac7a52c13ec
ms.openlocfilehash: 414998b4bef526060e7ba4f584fa071fbd0acaa5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33595870"
---
# <a name="auto-visual-basic"></a><span data-ttu-id="ea70e-102">Auto (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ea70e-102">Auto (Visual Basic)</span></span>
<span data-ttu-id="ea70e-103">指定 Visual Basic 应封送根据.NET Framework 规则基于所声明的外部过程的外部名称的字符串。</span><span class="sxs-lookup"><span data-stu-id="ea70e-103">Specifies that Visual Basic should marshal strings according to .NET Framework rules based on the external name of the external procedure being declared.</span></span>  
  
 <span data-ttu-id="ea70e-104">在调用在项目外部定义的过程时，Visual Basic 编译器没有访问它必须具有正确调用过程的信息。</span><span class="sxs-lookup"><span data-stu-id="ea70e-104">When you call a procedure defined outside your project, the Visual Basic compiler does not have access to the information it must have to call the procedure correctly.</span></span> <span data-ttu-id="ea70e-105">此信息包括过程所在的位置、 标识的方式、 其调用的序列和返回类型和字符串字符将其设置使用。</span><span class="sxs-lookup"><span data-stu-id="ea70e-105">This information includes where the procedure is located, how it is identified, its calling sequence and return type, and the string character set it uses.</span></span> <span data-ttu-id="ea70e-106">[声明语句](../../../visual-basic/language-reference/statements/declare-statement.md)创建对外部过程的引用，并提供这些必需的信息。</span><span class="sxs-lookup"><span data-stu-id="ea70e-106">The [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md) creates a reference to an external procedure and supplies this necessary information.</span></span>  
  
 <span data-ttu-id="ea70e-107">`charsetmodifier`部分`Declare`语句提供期间对外部过程的调用封送处理字符串的字符组信息。</span><span class="sxs-lookup"><span data-stu-id="ea70e-107">The `charsetmodifier` part in the `Declare` statement supplies the character set information for marshaling strings during a call to the external procedure.</span></span> <span data-ttu-id="ea70e-108">它还会影响 Visual Basic 会外部过程名称的外部文件的搜索。</span><span class="sxs-lookup"><span data-stu-id="ea70e-108">It also affects how Visual Basic searches the external file for the external procedure name.</span></span> <span data-ttu-id="ea70e-109">`Auto`修饰符指定 Visual Basic 应封送字符串根据.NET Framework 规则和，它应确定将运行时平台的和可能的基字符集修改外部过程名称，如果初始搜索无法正常工作。</span><span class="sxs-lookup"><span data-stu-id="ea70e-109">The `Auto` modifier specifies that Visual Basic should marshal strings according to .NET Framework rules, and that it should determine the base character set of the run-time platform and possibly modify the external procedure name if the initial search fails.</span></span> <span data-ttu-id="ea70e-110">有关详细信息，请参阅"字符集"[声明语句](../../../visual-basic/language-reference/statements/declare-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="ea70e-110">For more information, see "Character Sets" in [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md).</span></span>  
  
 <span data-ttu-id="ea70e-111">如果不指定任何字符集修饰符，则`Ansi`是默认设置。</span><span class="sxs-lookup"><span data-stu-id="ea70e-111">If no character set modifier is specified, `Ansi` is the default.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ea70e-112">备注</span><span class="sxs-lookup"><span data-stu-id="ea70e-112">Remarks</span></span>  
 <span data-ttu-id="ea70e-113">`Auto`修饰符可用于在此上下文中：</span><span class="sxs-lookup"><span data-stu-id="ea70e-113">The `Auto` modifier can be used in this context:</span></span>  
  
 [<span data-ttu-id="ea70e-114">Declare 语句</span><span class="sxs-lookup"><span data-stu-id="ea70e-114">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
## <a name="smart-device-developer-notes"></a><span data-ttu-id="ea70e-115">智能设备的开发人员说明</span><span class="sxs-lookup"><span data-stu-id="ea70e-115">Smart Device Developer Notes</span></span>  
 <span data-ttu-id="ea70e-116">此关键字不受支持。</span><span class="sxs-lookup"><span data-stu-id="ea70e-116">This keyword is not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea70e-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="ea70e-117">See Also</span></span>  
 [<span data-ttu-id="ea70e-118">Ansi</span><span class="sxs-lookup"><span data-stu-id="ea70e-118">Ansi</span></span>](../../../visual-basic/language-reference/modifiers/ansi.md)  
 [<span data-ttu-id="ea70e-119">Unicode</span><span class="sxs-lookup"><span data-stu-id="ea70e-119">Unicode</span></span>](../../../visual-basic/language-reference/modifiers/unicode.md)  
 [<span data-ttu-id="ea70e-120">关键字</span><span class="sxs-lookup"><span data-stu-id="ea70e-120">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
