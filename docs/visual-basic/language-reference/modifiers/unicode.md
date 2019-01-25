---
title: Unicode (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Unicode
helpviewer_keywords:
- Unicode, external references
- Declare statement [Visual Basic], marshaling strings
- Unicode keyword [Visual Basic]
- Unicode, marshaling strings
ms.assetid: 0021d5ff-3209-444e-8497-420f3e6ee075
ms.openlocfilehash: 491bbb24be8e6a3044b0a433c5ad262596ae00d8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54655278"
---
# <a name="unicode-visual-basic"></a><span data-ttu-id="23aeb-102">Unicode (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="23aeb-102">Unicode (Visual Basic)</span></span>
<span data-ttu-id="23aeb-103">指定 Visual Basic 应封送所有字符串转换为 Unicode 值，而不考虑所声明的外部过程的名称。</span><span class="sxs-lookup"><span data-stu-id="23aeb-103">Specifies that Visual Basic should marshal all strings to Unicode values regardless of the name of the external procedure being declared.</span></span>  
  
 <span data-ttu-id="23aeb-104">当调用在项目外部定义的过程时，Visual Basic 编译器没有访问它必须具有才能正确调用该过程的信息。</span><span class="sxs-lookup"><span data-stu-id="23aeb-104">When you call a procedure defined outside your project, the Visual Basic compiler does not have access to the information it must have in order to call the procedure correctly.</span></span> <span data-ttu-id="23aeb-105">此信息包括该过程所在的位置、 如何标识、 其调用的序列和返回类型和字符串字符将其设置使用。</span><span class="sxs-lookup"><span data-stu-id="23aeb-105">This information includes where the procedure is located, how it is identified, its calling sequence and return type, and the string character set it uses.</span></span> <span data-ttu-id="23aeb-106">[Declare 语句](../../../visual-basic/language-reference/statements/declare-statement.md)创建对外部过程的引用，并提供这些必需的信息。</span><span class="sxs-lookup"><span data-stu-id="23aeb-106">The [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md) creates a reference to an external procedure and supplies this necessary information.</span></span>  
  
 <span data-ttu-id="23aeb-107">`charsetmodifier`部分中`Declare`语句提供对外部过程的调用期间的封送字符串的字符组信息。</span><span class="sxs-lookup"><span data-stu-id="23aeb-107">The `charsetmodifier` part in the `Declare` statement supplies the character set information to marshal strings during a call to the external procedure.</span></span> <span data-ttu-id="23aeb-108">它还会影响 Visual Basic 如何搜索外部过程的名称的外部文件。</span><span class="sxs-lookup"><span data-stu-id="23aeb-108">It also affects how Visual Basic searches the external file for the external procedure name.</span></span> <span data-ttu-id="23aeb-109">`Unicode`修饰符指定 Visual Basic 应封送为 Unicode 值的所有字符串，并应查找而无需在搜索过程中修改其名称的过程。</span><span class="sxs-lookup"><span data-stu-id="23aeb-109">The `Unicode` modifier specifies that Visual Basic should marshal all strings to Unicode values and should look up the procedure without modifying its name during the search.</span></span>  
  
 <span data-ttu-id="23aeb-110">如果指定没有字符集修饰符，则`Ansi`是默认值。</span><span class="sxs-lookup"><span data-stu-id="23aeb-110">If no character set modifier is specified, `Ansi` is the default.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="23aeb-111">备注</span><span class="sxs-lookup"><span data-stu-id="23aeb-111">Remarks</span></span>  
 <span data-ttu-id="23aeb-112">`Unicode`修饰符可用于在此上下文中：</span><span class="sxs-lookup"><span data-stu-id="23aeb-112">The `Unicode` modifier can be used in this context:</span></span>  
  
 [<span data-ttu-id="23aeb-113">Declare 语句</span><span class="sxs-lookup"><span data-stu-id="23aeb-113">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
## <a name="smart-device-developer-notes"></a><span data-ttu-id="23aeb-114">智能设备开发人员说明</span><span class="sxs-lookup"><span data-stu-id="23aeb-114">Smart Device Developer Notes</span></span>  
 <span data-ttu-id="23aeb-115">不支持此关键字。</span><span class="sxs-lookup"><span data-stu-id="23aeb-115">This keyword is not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23aeb-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="23aeb-116">See also</span></span>
- [<span data-ttu-id="23aeb-117">Ansi</span><span class="sxs-lookup"><span data-stu-id="23aeb-117">Ansi</span></span>](../../../visual-basic/language-reference/modifiers/ansi.md)
- [<span data-ttu-id="23aeb-118">Auto</span><span class="sxs-lookup"><span data-stu-id="23aeb-118">Auto</span></span>](../../../visual-basic/language-reference/modifiers/auto.md)
- [<span data-ttu-id="23aeb-119">关键字</span><span class="sxs-lookup"><span data-stu-id="23aeb-119">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
