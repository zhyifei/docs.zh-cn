---
title: 未定义 Sub 或 Function (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vbrID35
ms.assetid: 661fdb90-ee7d-40ce-b30b-5e7267bd957a
ms.openlocfilehash: 58e90d769d5a7f2d88b5c27d1ec7d0d28c8d7b03
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33593696"
---
# <a name="sub-or-function-not-defined-visual-basic"></a><span data-ttu-id="3e445-102">未定义 Sub 或 Function (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3e445-102">Sub or Function not defined (Visual Basic)</span></span>
<span data-ttu-id="3e445-103">A`Sub`或`Function`必须定义为了调用。</span><span class="sxs-lookup"><span data-stu-id="3e445-103">A `Sub` or `Function` must be defined in order to be called.</span></span> <span data-ttu-id="3e445-104">此错误的可能原因包括：</span><span class="sxs-lookup"><span data-stu-id="3e445-104">Possible causes of this error include:</span></span>  
  
-   <span data-ttu-id="3e445-105">过程名称拼写错误。</span><span class="sxs-lookup"><span data-stu-id="3e445-105">Misspelling the procedure name.</span></span>  
  
-   <span data-ttu-id="3e445-106">尝试调用另一个项目中的过程，而无需显式添加到该项目中的引用**引用**对话框。</span><span class="sxs-lookup"><span data-stu-id="3e445-106">Trying to call a procedure from another project without explicitly adding a reference to that project in the **References** dialog box.</span></span>  
  
-   <span data-ttu-id="3e445-107">指定一个对的调用的过程不可见的过程。</span><span class="sxs-lookup"><span data-stu-id="3e445-107">Specifying a procedure that is not visible to the calling procedure.</span></span>  
  
-   <span data-ttu-id="3e445-108">声明的 Windows 动态链接库 (DLL) 例程或 Macintosh 代码资源例程不在指定的库或代码资源中。</span><span class="sxs-lookup"><span data-stu-id="3e445-108">Declaring a Windows dynamic-link library (DLL) routine or Macintosh code-resource routine that is not in the specified library or code resource.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="3e445-109">更正此错误</span><span class="sxs-lookup"><span data-stu-id="3e445-109">To correct this error</span></span>  
  
1.  <span data-ttu-id="3e445-110">请确保过程名称拼写正确。</span><span class="sxs-lookup"><span data-stu-id="3e445-110">Make sure that the procedure name is spelled correctly.</span></span>  
  
2.  <span data-ttu-id="3e445-111">找到包含你想要调用的过程的项目的名称**引用**对话框。</span><span class="sxs-lookup"><span data-stu-id="3e445-111">Find the name of the project containing the procedure you want to call in the **References** dialog box.</span></span> <span data-ttu-id="3e445-112">如果没有出现，请单击**浏览**按钮对其进行搜索。</span><span class="sxs-lookup"><span data-stu-id="3e445-112">If it does not appear, click the **Browse** button to search for it.</span></span> <span data-ttu-id="3e445-113">选择的项目名称，左边的复选框，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="3e445-113">Select the check box to the left of the project name, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="3e445-114">请检查该例程的名称。</span><span class="sxs-lookup"><span data-stu-id="3e445-114">Check the name of the routine.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e445-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="3e445-115">See Also</span></span>  
 [<span data-ttu-id="3e445-116">错误类型</span><span class="sxs-lookup"><span data-stu-id="3e445-116">Error Types</span></span>](../../../visual-basic/programming-guide/language-features/error-types.md)  
 [<span data-ttu-id="3e445-117">管理项目中的引用</span><span class="sxs-lookup"><span data-stu-id="3e445-117">Managing references in a project</span></span>](/visualstudio/ide/managing-references-in-a-project)  
 [<span data-ttu-id="3e445-118">Sub 语句</span><span class="sxs-lookup"><span data-stu-id="3e445-118">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
 [<span data-ttu-id="3e445-119">Function 语句</span><span class="sxs-lookup"><span data-stu-id="3e445-119">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)
