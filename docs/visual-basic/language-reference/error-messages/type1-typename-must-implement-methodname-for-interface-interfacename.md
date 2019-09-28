---
title: <type1>“<typename>”必须为接口“<interfacename>”实现“<methodname>”
ms.date: 07/20/2015
f1_keywords:
- vbc30149
- bc30149
helpviewer_keywords:
- BC30149
ms.assetid: 29d1b7f4-dca7-478c-bbe7-c657f342c183
ms.openlocfilehash: c387b0225375f4675042bef593b23a084305b4fd
ms.sourcegitcommit: 35da8fb45b4cca4e59cc99a5c56262c356977159
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/28/2019
ms.locfileid: "71591595"
---
# <a name="type1typename-must-implement-methodname-for-interface-interfacename"></a><span data-ttu-id="420e2-102">\<type1 > "\<typename >" 必须为接口 "\<interfacename >" 实现 "2methodname @no__t"</span><span class="sxs-lookup"><span data-stu-id="420e2-102">\<type1>'\<typename>' must implement '\<methodname>' for interface '\<interfacename>'</span></span>
<span data-ttu-id="420e2-103">类或结构声明实现接口，但不实现由接口定义的过程。</span><span class="sxs-lookup"><span data-stu-id="420e2-103">A class or structure claims to implement an interface but does not implement a procedure defined by the interface.</span></span> <span data-ttu-id="420e2-104">必须实现接口的每个成员。</span><span class="sxs-lookup"><span data-stu-id="420e2-104">Every member of the interface must be implemented.</span></span>  
  
 <span data-ttu-id="420e2-105">**错误 ID：** BC30149</span><span class="sxs-lookup"><span data-stu-id="420e2-105">**Error ID:** BC30149</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="420e2-106">更正此错误</span><span class="sxs-lookup"><span data-stu-id="420e2-106">To correct this error</span></span>  
  
1. <span data-ttu-id="420e2-107">使用在接口中定义的相同名称和签名声明过程。</span><span class="sxs-lookup"><span data-stu-id="420e2-107">Declare a procedure with the same name and signature as defined in the interface.</span></span> <span data-ttu-id="420e2-108">请确保至少包含 `End Function` 或 @no__t。</span><span class="sxs-lookup"><span data-stu-id="420e2-108">Be sure to include at least the `End Function` or `End Sub` statement.</span></span>  
  
2. <span data-ttu-id="420e2-109">将 `Implements` 子句添加到 @no__t 或 @no__t 语句的末尾。</span><span class="sxs-lookup"><span data-stu-id="420e2-109">Add an `Implements` clause to the end of the `Function` or `Sub` statement.</span></span> <span data-ttu-id="420e2-110">例如：</span><span class="sxs-lookup"><span data-stu-id="420e2-110">For example:</span></span>  
  
    ```vb  
    Public Sub DoSomething() Implements IBaseInterface.DoSomething  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="420e2-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="420e2-111">See also</span></span>

- [<span data-ttu-id="420e2-112">Implements 语句</span><span class="sxs-lookup"><span data-stu-id="420e2-112">Implements Statement</span></span>](../../../visual-basic/language-reference/statements/implements-statement.md)
- [<span data-ttu-id="420e2-113">接口</span><span class="sxs-lookup"><span data-stu-id="420e2-113">Interfaces</span></span>](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
