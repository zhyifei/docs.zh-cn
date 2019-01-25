---
title: Ansi (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Ansi
helpviewer_keywords:
- Declare statement [Visual Basic], marshaling strings [Visual Basic]
- ANSI, Visual Basic
- ANSI
ms.assetid: 4f1fa6ff-5557-41ab-b6da-90baf4c15917
ms.openlocfilehash: e474bd686cc753a0265df1fc2914a73d1b62f1b5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54737317"
---
# <a name="ansi-visual-basic"></a><span data-ttu-id="ec310-102">Ansi (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ec310-102">Ansi (Visual Basic)</span></span>
<span data-ttu-id="ec310-103">指定 Visual Basic 应封送到美国国家标准协会 (ANSI) 值，而不考虑所声明的外部过程的名称的所有字符串。</span><span class="sxs-lookup"><span data-stu-id="ec310-103">Specifies that Visual Basic should marshal all strings to American National Standards Institute (ANSI) values regardless of the name of the external procedure being declared.</span></span>  
  
 <span data-ttu-id="ec310-104">当调用在项目外部定义的过程时，Visual Basic 编译器没有访问正确调用该过程所需的信息。</span><span class="sxs-lookup"><span data-stu-id="ec310-104">When you call a procedure defined outside your project, the Visual Basic compiler does not have access to the information it needs to call the procedure correctly.</span></span> <span data-ttu-id="ec310-105">此信息包括该过程所在的位置、 如何标识、 其调用的序列和返回类型和字符串字符将其设置使用。</span><span class="sxs-lookup"><span data-stu-id="ec310-105">This information includes where the procedure is located, how it is identified, its calling sequence and return type, and the string character set it uses.</span></span> <span data-ttu-id="ec310-106">[Declare 语句](../../../visual-basic/language-reference/statements/declare-statement.md)创建对外部过程的引用，并提供这些必需的信息。</span><span class="sxs-lookup"><span data-stu-id="ec310-106">The [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md) creates a reference to an external procedure and supplies this necessary information.</span></span>  
  
 <span data-ttu-id="ec310-107">`charsetmodifier`部分中`Declare`语句提供了有关期间对外部过程的调用封送处理字符串的字符组信息。</span><span class="sxs-lookup"><span data-stu-id="ec310-107">The `charsetmodifier` part in the `Declare` statement supplies the character set information for marshaling strings during a call to the external procedure.</span></span> <span data-ttu-id="ec310-108">它还会影响 Visual Basic 如何搜索外部过程的名称的外部文件。</span><span class="sxs-lookup"><span data-stu-id="ec310-108">It also affects how Visual Basic searches the external file for the external procedure name.</span></span> <span data-ttu-id="ec310-109">`Ansi`修饰符指定 Visual Basic 应封送为 ANSI 值的所有字符串，并应查找而无需在搜索过程中修改其名称的过程。</span><span class="sxs-lookup"><span data-stu-id="ec310-109">The `Ansi` modifier specifies that Visual Basic should marshal all strings to ANSI values and should look up the procedure without modifying its name during the search.</span></span>  
  
 <span data-ttu-id="ec310-110">如果指定没有字符集修饰符，则`Ansi`是默认值。</span><span class="sxs-lookup"><span data-stu-id="ec310-110">If no character set modifier is specified, `Ansi` is the default.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ec310-111">备注</span><span class="sxs-lookup"><span data-stu-id="ec310-111">Remarks</span></span>  
 <span data-ttu-id="ec310-112">`Ansi`修饰符可用于在此上下文中：</span><span class="sxs-lookup"><span data-stu-id="ec310-112">The `Ansi` modifier can be used in this context:</span></span>  
  
 [<span data-ttu-id="ec310-113">Declare 语句</span><span class="sxs-lookup"><span data-stu-id="ec310-113">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
## <a name="smart-device-developer-notes"></a><span data-ttu-id="ec310-114">智能设备开发人员说明</span><span class="sxs-lookup"><span data-stu-id="ec310-114">Smart Device Developer Notes</span></span>  
 <span data-ttu-id="ec310-115">不支持此关键字。</span><span class="sxs-lookup"><span data-stu-id="ec310-115">This keyword is not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec310-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="ec310-116">See also</span></span>
- [<span data-ttu-id="ec310-117">Auto</span><span class="sxs-lookup"><span data-stu-id="ec310-117">Auto</span></span>](../../../visual-basic/language-reference/modifiers/auto.md)
- [<span data-ttu-id="ec310-118">Unicode</span><span class="sxs-lookup"><span data-stu-id="ec310-118">Unicode</span></span>](../../../visual-basic/language-reference/modifiers/unicode.md)
- [<span data-ttu-id="ec310-119">关键字</span><span class="sxs-lookup"><span data-stu-id="ec310-119">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
