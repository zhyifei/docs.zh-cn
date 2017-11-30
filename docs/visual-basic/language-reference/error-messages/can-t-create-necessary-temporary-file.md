---
title: "可以 &#39; t 创建必要的临时文件"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vbrID322
ms.assetid: 53617b5b-eb06-4188-b4c2-8607cb9fbc79
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: dbb1c65318f954249da097b026583b09ad340e20
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="can39t-create-necessary-temporary-file"></a><span data-ttu-id="d2f61-102">可以 &#39; t 创建必要的临时文件</span><span class="sxs-lookup"><span data-stu-id="d2f61-102">Can&#39;t create necessary temporary file</span></span>
<span data-ttu-id="d2f61-103">其中一个驱动器已满，其中包含由 TEMP 环境变量，指定的目录或 TEMP 环境变量指定的无效或只读驱动器或目录。</span><span class="sxs-lookup"><span data-stu-id="d2f61-103">Either the drive is full that contains the directory specified by the TEMP environment variable, or the TEMP environment variable specifies an invalid or read-only drive or directory.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="d2f61-104">更正此错误</span><span class="sxs-lookup"><span data-stu-id="d2f61-104">To correct this error</span></span>  
  
1.  <span data-ttu-id="d2f61-105">如果完整驱动器区分开，删除文件。</span><span class="sxs-lookup"><span data-stu-id="d2f61-105">Delete files from the drive, if full.</span></span>  
  
2.  <span data-ttu-id="d2f61-106">TEMP 环境变量中指定一个不同的驱动器。</span><span class="sxs-lookup"><span data-stu-id="d2f61-106">Specify a different drive in the TEMP environment variable.</span></span>  
  
3.  <span data-ttu-id="d2f61-107">指定有效的驱动器 TEMP 环境变量。</span><span class="sxs-lookup"><span data-stu-id="d2f61-107">Specify a valid drive for the TEMP environment variable.</span></span>  
  
4.  <span data-ttu-id="d2f61-108">从当前指定的驱动器或目录中删除只读的限制。</span><span class="sxs-lookup"><span data-stu-id="d2f61-108">Remove the read-only restriction from the currently specified drive or directory.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2f61-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d2f61-109">See Also</span></span>  
 [<span data-ttu-id="d2f61-110">错误类型</span><span class="sxs-lookup"><span data-stu-id="d2f61-110">Error Types</span></span>](../../../visual-basic/programming-guide/language-features/error-types.md)
