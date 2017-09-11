---
title: "Sub 或 Function 未定义 (Visual Basic 中) |Microsoft 文档"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrID35
dev_langs:
- VB
ms.assetid: 661fdb90-ee7d-40ce-b30b-5e7267bd957a
caps.latest.revision: 12
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
ms.openlocfilehash: 837beec039e1fb8f8a796b2781d93de6d4cfb33a
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="sub-or-function-not-defined-visual-basic"></a><span data-ttu-id="3485f-102">未定义 Sub 或 Function (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3485f-102">Sub or Function not defined (Visual Basic)</span></span>
<span data-ttu-id="3485f-103">一个`Sub`或`Function`必须定义以便进行调用。</span><span class="sxs-lookup"><span data-stu-id="3485f-103">A `Sub` or `Function` must be defined in order to be called.</span></span> <span data-ttu-id="3485f-104">此错误的可能原因包括：</span><span class="sxs-lookup"><span data-stu-id="3485f-104">Possible causes of this error include:</span></span>  
  
-   <span data-ttu-id="3485f-105">过程名称拼写错误。</span><span class="sxs-lookup"><span data-stu-id="3485f-105">Misspelling the procedure name.</span></span>  
  
-   <span data-ttu-id="3485f-106">尝试从另一个项目中调用的过程，而无需显式添加到该项目中引用**引用**对话框。</span><span class="sxs-lookup"><span data-stu-id="3485f-106">Trying to call a procedure from another project without explicitly adding a reference to that project in the **References** dialog box.</span></span>  
  
-   <span data-ttu-id="3485f-107">指定对调用的过程是不可见的过程。</span><span class="sxs-lookup"><span data-stu-id="3485f-107">Specifying a procedure that is not visible to the calling procedure.</span></span>  
  
-   <span data-ttu-id="3485f-108">声明的 Windows 动态链接库 (DLL) 例程或不在指定的库或代码资源的 Macintosh 代码资源例程。</span><span class="sxs-lookup"><span data-stu-id="3485f-108">Declaring a Windows dynamic-link library (DLL) routine or Macintosh code-resource routine that is not in the specified library or code resource.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="3485f-109">更正此错误</span><span class="sxs-lookup"><span data-stu-id="3485f-109">To correct this error</span></span>  
  
1.  <span data-ttu-id="3485f-110">请确保过程名称拼写正确。</span><span class="sxs-lookup"><span data-stu-id="3485f-110">Make sure that the procedure name is spelled correctly.</span></span>  
  
2.  <span data-ttu-id="3485f-111">找到包含你想要调用的过程的项目名称**引用**对话框。</span><span class="sxs-lookup"><span data-stu-id="3485f-111">Find the name of the project containing the procedure you want to call in the **References** dialog box.</span></span> <span data-ttu-id="3485f-112">如果未出现，请单击**浏览**按钮对其进行搜索。</span><span class="sxs-lookup"><span data-stu-id="3485f-112">If it does not appear, click the **Browse** button to search for it.</span></span> <span data-ttu-id="3485f-113">选择的项目名称，左边的复选框，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="3485f-113">Select the check box to the left of the project name, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="3485f-114">请检查该例程的名称。</span><span class="sxs-lookup"><span data-stu-id="3485f-114">Check the name of the routine.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3485f-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3485f-115">See Also</span></span>  
 <span data-ttu-id="3485f-116">[错误类型](../../../visual-basic/programming-guide/language-features/error-types.md) </span><span class="sxs-lookup"><span data-stu-id="3485f-116">[Error Types](../../../visual-basic/programming-guide/language-features/error-types.md) </span></span>  
<span data-ttu-id="3485f-117"> [管理项目中引用](https://docs.microsoft.com/visualstudio/ide/managing-references-in-a-project) </span><span class="sxs-lookup"><span data-stu-id="3485f-117"> [Managing references in a project](https://docs.microsoft.com/visualstudio/ide/managing-references-in-a-project) </span></span>  
<span data-ttu-id="3485f-118"> [Sub 语句](../../../visual-basic/language-reference/statements/sub-statement.md) </span><span class="sxs-lookup"><span data-stu-id="3485f-118"> [Sub Statement](../../../visual-basic/language-reference/statements/sub-statement.md) </span></span>  
<span data-ttu-id="3485f-119"> [Function 语句](../../../visual-basic/language-reference/statements/function-statement.md)</span><span class="sxs-lookup"><span data-stu-id="3485f-119"> [Function Statement](../../../visual-basic/language-reference/statements/function-statement.md)</span></span>
