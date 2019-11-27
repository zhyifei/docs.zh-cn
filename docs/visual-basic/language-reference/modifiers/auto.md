---
title: Auto
ms.date: 07/20/2015
f1_keywords:
- vb.Auto
helpviewer_keywords:
- Auto keyword [Visual Basic], external references
- Declare statement [Visual Basic], marshaling strings
- Auto keyword [Visual Basic]
- Auto keyword [Visual Basic], marshaling strings
ms.assetid: bf79ba95-a62c-48a5-916f-0ac7a52c13ec
ms.openlocfilehash: 7ea46e5f8b882bb986f23e792b240bad0c5be7a5
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351622"
---
# <a name="auto-visual-basic"></a><span data-ttu-id="a6fc7-102">Auto (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a6fc7-102">Auto (Visual Basic)</span></span>
<span data-ttu-id="a6fc7-103">指定 Visual Basic 应根据正在声明的外部过程的外部名称按 .NET Framework 规则封送字符串。</span><span class="sxs-lookup"><span data-stu-id="a6fc7-103">Specifies that Visual Basic should marshal strings according to .NET Framework rules based on the external name of the external procedure being declared.</span></span>  
  
 <span data-ttu-id="a6fc7-104">调用在项目外部定义的过程时，Visual Basic 编译器不能访问正确调用过程所必须具有的信息。</span><span class="sxs-lookup"><span data-stu-id="a6fc7-104">When you call a procedure defined outside your project, the Visual Basic compiler does not have access to the information it must have to call the procedure correctly.</span></span> <span data-ttu-id="a6fc7-105">此信息包括过程的位置、标识方法、调用序列和返回类型，以及它使用的字符串字符集。</span><span class="sxs-lookup"><span data-stu-id="a6fc7-105">This information includes where the procedure is located, how it is identified, its calling sequence and return type, and the string character set it uses.</span></span> <span data-ttu-id="a6fc7-106">[Declare 语句](../../../visual-basic/language-reference/statements/declare-statement.md)创建对外部过程的引用并提供此必要信息。</span><span class="sxs-lookup"><span data-stu-id="a6fc7-106">The [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md) creates a reference to an external procedure and supplies this necessary information.</span></span>  
  
 <span data-ttu-id="a6fc7-107">`Declare` 语句中 `charsetmodifier` 部分提供了在调用外部过程期间封送处理字符串的字符集信息。</span><span class="sxs-lookup"><span data-stu-id="a6fc7-107">The `charsetmodifier` part in the `Declare` statement supplies the character set information for marshaling strings during a call to the external procedure.</span></span> <span data-ttu-id="a6fc7-108">它还会影响 Visual Basic 搜索外部文件的外部过程名称的方式。</span><span class="sxs-lookup"><span data-stu-id="a6fc7-108">It also affects how Visual Basic searches the external file for the external procedure name.</span></span> <span data-ttu-id="a6fc7-109">`Auto` 修饰符指定 Visual Basic 应根据 .NET Framework 规则封送字符串，并且应确定运行时平台的基本字符集，并可能在初始搜索失败时修改外部过程名称。</span><span class="sxs-lookup"><span data-stu-id="a6fc7-109">The `Auto` modifier specifies that Visual Basic should marshal strings according to .NET Framework rules, and that it should determine the base character set of the run-time platform and possibly modify the external procedure name if the initial search fails.</span></span> <span data-ttu-id="a6fc7-110">有关详细信息，请参阅[Declare 语句](../../../visual-basic/language-reference/statements/declare-statement.md)中的 "字符集"。</span><span class="sxs-lookup"><span data-stu-id="a6fc7-110">For more information, see "Character Sets" in [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md).</span></span>  
  
 <span data-ttu-id="a6fc7-111">如果未指定字符集修饰符，则默认值为 `Ansi`。</span><span class="sxs-lookup"><span data-stu-id="a6fc7-111">If no character set modifier is specified, `Ansi` is the default.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a6fc7-112">备注</span><span class="sxs-lookup"><span data-stu-id="a6fc7-112">Remarks</span></span>  
 <span data-ttu-id="a6fc7-113">`Auto` 修饰符可用于以下上下文：</span><span class="sxs-lookup"><span data-stu-id="a6fc7-113">The `Auto` modifier can be used in this context:</span></span>  
  
 [<span data-ttu-id="a6fc7-114">Declare Statement</span><span class="sxs-lookup"><span data-stu-id="a6fc7-114">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
## <a name="smart-device-developer-notes"></a><span data-ttu-id="a6fc7-115">智能设备开发人员说明</span><span class="sxs-lookup"><span data-stu-id="a6fc7-115">Smart Device Developer Notes</span></span>  
 <span data-ttu-id="a6fc7-116">不支持此关键字。</span><span class="sxs-lookup"><span data-stu-id="a6fc7-116">This keyword is not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6fc7-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a6fc7-117">See also</span></span>

- [<span data-ttu-id="a6fc7-118">Ansi</span><span class="sxs-lookup"><span data-stu-id="a6fc7-118">Ansi</span></span>](../../../visual-basic/language-reference/modifiers/ansi.md)
- [<span data-ttu-id="a6fc7-119">Unicode</span><span class="sxs-lookup"><span data-stu-id="a6fc7-119">Unicode</span></span>](../../../visual-basic/language-reference/modifiers/unicode.md)
- [<span data-ttu-id="a6fc7-120">关键字</span><span class="sxs-lookup"><span data-stu-id="a6fc7-120">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
