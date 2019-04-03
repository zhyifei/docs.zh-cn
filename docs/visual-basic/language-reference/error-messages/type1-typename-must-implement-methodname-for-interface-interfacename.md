---
title: <type1>'<typename>必须实现<methodname>for interface<interfacename>
ms.date: 07/20/2015
f1_keywords:
- vbc30149
- bc30149
helpviewer_keywords:
- BC30149
ms.assetid: 29d1b7f4-dca7-478c-bbe7-c657f342c183
ms.openlocfilehash: b8bcb16798284a09608ba6942226ef07c6859d4f
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2019
ms.locfileid: "58824190"
---
# <a name="type1typename-must-implement-methodname-for-interface-interfacename"></a><span data-ttu-id="bf4a4-102">\<类型 1 >\<类型名称 > 必须实现\<m h o d > 接口\<interfacename ></span><span class="sxs-lookup"><span data-stu-id="bf4a4-102">\<type1>'\<typename>' must implement '\<methodname>' for interface '\<interfacename>'</span></span>
<span data-ttu-id="bf4a4-103">类或结构声明实现一个接口，但不实现的接口定义的过程。</span><span class="sxs-lookup"><span data-stu-id="bf4a4-103">A class or structure claims to implement an interface but does not implement a procedure defined by the interface.</span></span> <span data-ttu-id="bf4a4-104">必须实现该接口的每个成员。</span><span class="sxs-lookup"><span data-stu-id="bf4a4-104">Every member of the interface must be implemented.</span></span>  
  
 <span data-ttu-id="bf4a4-105">**错误 ID:** BC30149</span><span class="sxs-lookup"><span data-stu-id="bf4a4-105">**Error ID:** BC30149</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="bf4a4-106">更正此错误</span><span class="sxs-lookup"><span data-stu-id="bf4a4-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="bf4a4-107">声明具有相同名称和签名，因为在接口中定义的过程。</span><span class="sxs-lookup"><span data-stu-id="bf4a4-107">Declare a procedure with the same name and signature as defined in the interface.</span></span> <span data-ttu-id="bf4a4-108">请务必包括至少`End Function`或`End Sub`语句。</span><span class="sxs-lookup"><span data-stu-id="bf4a4-108">Be sure to include at least the `End Function` or `End Sub` statement.</span></span>  
  
2.  <span data-ttu-id="bf4a4-109">添加`Implements`子句的末尾`Function`或`Sub`语句。</span><span class="sxs-lookup"><span data-stu-id="bf4a4-109">Add an `Implements` clause to the end of the `Function` or `Sub` statement.</span></span> <span data-ttu-id="bf4a4-110">例如：</span><span class="sxs-lookup"><span data-stu-id="bf4a4-110">For example:</span></span>  
  
    ```  
    Public Sub DoSomething() Implements IBaseInterface.DoSomething  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="bf4a4-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="bf4a4-111">See also</span></span>

- [<span data-ttu-id="bf4a4-112">Implements 语句</span><span class="sxs-lookup"><span data-stu-id="bf4a4-112">Implements Statement</span></span>](../../../visual-basic/language-reference/statements/implements-statement.md)
- [<span data-ttu-id="bf4a4-113">接口</span><span class="sxs-lookup"><span data-stu-id="bf4a4-113">Interfaces</span></span>](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
