---
title: <type1>“<typename>”必须为接口“<membername>”实现“<interfacename>”
ms.date: 07/20/2015
f1_keywords:
- vbc30154
- bc30154
helpviewer_keywords:
- BC30154
ms.assetid: 259afdfa-3608-4760-adcb-88ec0da5020d
ms.openlocfilehash: de7dd9026e08495941a89be0db11ad4c68d2a748
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/30/2019
ms.locfileid: "55264227"
---
# <a name="type1typename-must-implement-membername-for-interface-interfacename"></a><span data-ttu-id="d04b0-102">\<类型 1 >\<类型名称 > 必须实现\<成员名称 > 接口\<interfacename ></span><span class="sxs-lookup"><span data-stu-id="d04b0-102">\<type1>'\<typename>' must implement '\<membername>' for interface '\<interfacename>'</span></span>
<span data-ttu-id="d04b0-103">'\<类型名称 > 必须实现\<成员名称 > 接口\<interfacename >。</span><span class="sxs-lookup"><span data-stu-id="d04b0-103">'\<typename>' must implement '\<membername>' for interface '\<interfacename>'.</span></span> <span data-ttu-id="d04b0-104">实现属性必须具有匹配的 ReadOnly / WriteOnly 说明符。</span><span class="sxs-lookup"><span data-stu-id="d04b0-104">Implementing property must have matching 'ReadOnly'/'WriteOnly' specifiers.</span></span>  
  
 <span data-ttu-id="d04b0-105">类或结构声明实现一个接口，但不实现过程、 属性或事件的接口定义。</span><span class="sxs-lookup"><span data-stu-id="d04b0-105">A class or structure claims to implement an interface but does not implement a procedure, property, or event defined by the interface.</span></span> <span data-ttu-id="d04b0-106">必须实现该接口的每个成员。</span><span class="sxs-lookup"><span data-stu-id="d04b0-106">Every member of the interface must be implemented.</span></span>  
  
 <span data-ttu-id="d04b0-107">**错误 ID:** BC30154</span><span class="sxs-lookup"><span data-stu-id="d04b0-107">**Error ID:** BC30154</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="d04b0-108">更正此错误</span><span class="sxs-lookup"><span data-stu-id="d04b0-108">To correct this error</span></span>  
  
1.  <span data-ttu-id="d04b0-109">声明具有相同名称和签名，因为在接口中定义的成员。</span><span class="sxs-lookup"><span data-stu-id="d04b0-109">Declare a member with the same name and signature as defined in the interface.</span></span> <span data-ttu-id="d04b0-110">请务必包括至少`End Function`， `End Sub`，或`End Property`语句。</span><span class="sxs-lookup"><span data-stu-id="d04b0-110">Be sure to include at least the `End Function`, `End Sub`, or `End Property` statement.</span></span>  
  
2.  <span data-ttu-id="d04b0-111">添加`Implements`子句的末尾`Function`， `Sub`， `Property`，或`Event`语句。</span><span class="sxs-lookup"><span data-stu-id="d04b0-111">Add an `Implements` clause to the end of the `Function`, `Sub`, `Property`, or `Event` statement.</span></span> <span data-ttu-id="d04b0-112">例如：</span><span class="sxs-lookup"><span data-stu-id="d04b0-112">For example:</span></span>  
  
    ```  
    Public Event ItHappened() Implements IBaseInterface.ItHappened  
    ```  
  
3.  <span data-ttu-id="d04b0-113">当实现属性，请确保`ReadOnly`或`WriteOnly`使用如下所示的接口定义的方式相同。</span><span class="sxs-lookup"><span data-stu-id="d04b0-113">When implementing a property, make sure that `ReadOnly` or `WriteOnly` is used in the same way as in the interface definition.</span></span>  
  
4.  <span data-ttu-id="d04b0-114">当实现属性，将声明`Get`和`Set`过程，根据需要。</span><span class="sxs-lookup"><span data-stu-id="d04b0-114">When implementing a property, declare `Get` and `Set` procedures, as appropriate.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d04b0-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="d04b0-115">See also</span></span>
- [<span data-ttu-id="d04b0-116">Implements 语句</span><span class="sxs-lookup"><span data-stu-id="d04b0-116">Implements Statement</span></span>](../../../visual-basic/language-reference/statements/implements-statement.md)
- [<span data-ttu-id="d04b0-117">接口</span><span class="sxs-lookup"><span data-stu-id="d04b0-117">Interfaces</span></span>](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
