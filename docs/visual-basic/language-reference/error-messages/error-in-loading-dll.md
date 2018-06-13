---
title: 加载 DLL 时出错 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vbrID48
ms.assetid: 4226cd1f-028c-477d-88a5-cb57f7e0cdc8
ms.openlocfilehash: ac21c4d52b248025ee26bac3e511bb5b0a0b668e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33584678"
---
# <a name="error-in-loading-dll-visual-basic"></a><span data-ttu-id="d5bce-102">加载 DLL 时出错 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d5bce-102">Error in loading DLL (Visual Basic)</span></span>
<span data-ttu-id="d5bce-103">动态链接库 (DLL) 是中指定一个库`Lib`子句`Declare`语句。</span><span class="sxs-lookup"><span data-stu-id="d5bce-103">A dynamic-link library (DLL) is a library specified in the `Lib` clause of a `Declare` statement.</span></span> <span data-ttu-id="d5bce-104">此错误的可能原因包括：</span><span class="sxs-lookup"><span data-stu-id="d5bce-104">Possible causes for this error include:</span></span>  
  
-   <span data-ttu-id="d5bce-105">文件不是可执行的 DLL。</span><span class="sxs-lookup"><span data-stu-id="d5bce-105">The file is not DLL executable.</span></span>  
  
-   <span data-ttu-id="d5bce-106">文件不是 Microsoft Windows DLL。</span><span class="sxs-lookup"><span data-stu-id="d5bce-106">The file is not a Microsoft Windows DLL.</span></span>  
  
-   <span data-ttu-id="d5bce-107">DLL 引用不存在的另一个 DLL。</span><span class="sxs-lookup"><span data-stu-id="d5bce-107">The DLL references another DLL that is not present.</span></span>  
  
-   <span data-ttu-id="d5bce-108">DLL 或引用的 DLL 不在路径中指定的目录。</span><span class="sxs-lookup"><span data-stu-id="d5bce-108">The DLL or referenced DLL is not in a directory specified in the path.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="d5bce-109">更正此错误</span><span class="sxs-lookup"><span data-stu-id="d5bce-109">To correct this error</span></span>  
  
-   <span data-ttu-id="d5bce-110">如果源文本文件，因此不 DLL 的可执行文件，该文件，它必须为编译并链接到 DLL 的可执行文件窗体。</span><span class="sxs-lookup"><span data-stu-id="d5bce-110">If the file is a source-text file and therefore not DLL executable, it must be compiled and linked to a DLL-executable form.</span></span>  
  
-   <span data-ttu-id="d5bce-111">如果文件不是 Microsoft Windows DLL，获取 Microsoft Windows 等效。</span><span class="sxs-lookup"><span data-stu-id="d5bce-111">If the file is not a Microsoft Windows DLL, obtain the Microsoft Windows equivalent.</span></span>  
  
-   <span data-ttu-id="d5bce-112">如果 DLL 引用不存在的另一个 DLL，获取引用的 DLL 并使其可用。</span><span class="sxs-lookup"><span data-stu-id="d5bce-112">If the DLL references another DLL that is not present, obtain the referenced DLL and make it available.</span></span>  
  
-   <span data-ttu-id="d5bce-113">如果 DLL 或引用的 DLL 不是指定的路径的目录，请将 DLL 移动到引用的目录。</span><span class="sxs-lookup"><span data-stu-id="d5bce-113">If the DLL or referenced DLL is not in a directory specified by the path, move the DLL to a referenced directory.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5bce-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="d5bce-114">See Also</span></span>  
 [<span data-ttu-id="d5bce-115">Declare 语句</span><span class="sxs-lookup"><span data-stu-id="d5bce-115">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)
