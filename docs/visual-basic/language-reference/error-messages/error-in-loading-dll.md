---
title: 加载 DLL 时出错 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vbrID48
ms.assetid: 4226cd1f-028c-477d-88a5-cb57f7e0cdc8
ms.openlocfilehash: 5a26443a49b0b853f2f2188fb58d7ed907d671b4
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "64659628"
---
# <a name="error-in-loading-dll-visual-basic"></a><span data-ttu-id="10236-102">加载 DLL 时出错 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="10236-102">Error in loading DLL (Visual Basic)</span></span>
<span data-ttu-id="10236-103">动态链接库 (DLL) 是一个库中指定`Lib`子句`Declare`语句。</span><span class="sxs-lookup"><span data-stu-id="10236-103">A dynamic-link library (DLL) is a library specified in the `Lib` clause of a `Declare` statement.</span></span> <span data-ttu-id="10236-104">此错误的可能原因包括：</span><span class="sxs-lookup"><span data-stu-id="10236-104">Possible causes for this error include:</span></span>  
  
- <span data-ttu-id="10236-105">文件不是可执行文件的 DLL。</span><span class="sxs-lookup"><span data-stu-id="10236-105">The file is not DLL executable.</span></span>  
  
- <span data-ttu-id="10236-106">文件不是 Microsoft Windows DLL。</span><span class="sxs-lookup"><span data-stu-id="10236-106">The file is not a Microsoft Windows DLL.</span></span>  
  
- <span data-ttu-id="10236-107">DLL 引用不存在的另一个 DLL。</span><span class="sxs-lookup"><span data-stu-id="10236-107">The DLL references another DLL that is not present.</span></span>  
  
- <span data-ttu-id="10236-108">DLL 或引用的 DLL 不是在路径中指定的目录。</span><span class="sxs-lookup"><span data-stu-id="10236-108">The DLL or referenced DLL is not in a directory specified in the path.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="10236-109">更正此错误</span><span class="sxs-lookup"><span data-stu-id="10236-109">To correct this error</span></span>  
  
- <span data-ttu-id="10236-110">如果该文件是源文本文件，因此不 DLL 的可执行文件，它必须编译并链接到 DLL 的可执行文件窗体。</span><span class="sxs-lookup"><span data-stu-id="10236-110">If the file is a source-text file and therefore not DLL executable, it must be compiled and linked to a DLL-executable form.</span></span>  
  
- <span data-ttu-id="10236-111">如果文件不是 Microsoft Windows DLL，获取 Microsoft Windows 等效。</span><span class="sxs-lookup"><span data-stu-id="10236-111">If the file is not a Microsoft Windows DLL, obtain the Microsoft Windows equivalent.</span></span>  
  
- <span data-ttu-id="10236-112">如果 DLL 引用不存在的另一个 DLL，获取引用的 DLL 并使其可用。</span><span class="sxs-lookup"><span data-stu-id="10236-112">If the DLL references another DLL that is not present, obtain the referenced DLL and make it available.</span></span>  
  
- <span data-ttu-id="10236-113">如果 DLL 或引用的 DLL 不是由路径指定的目录中，将该 DLL 移动到引用的目录。</span><span class="sxs-lookup"><span data-stu-id="10236-113">If the DLL or referenced DLL is not in a directory specified by the path, move the DLL to a referenced directory.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10236-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="10236-114">See also</span></span>

- [<span data-ttu-id="10236-115">Declare 语句</span><span class="sxs-lookup"><span data-stu-id="10236-115">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)
