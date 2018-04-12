---
title: 无法将文件保存到 TEMP
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrID735
ms.assetid: 1055fc15-9641-43b2-a40c-a0a9fbbb34b2
caps.latest.revision: 7
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 3196f5f70405c6bf7ab8eda3d056c5a86eca57f5
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="cannot-save-file-to-temp"></a><span data-ttu-id="04690-102">无法将文件保存到 TEMP</span><span class="sxs-lookup"><span data-stu-id="04690-102">Cannot save file to TEMP</span></span>
<span data-ttu-id="04690-103">组件找不到名为 TEMP 目录，或者包含 TEMP 目录的驱动器或分区的空间不足，不能保存信息。</span><span class="sxs-lookup"><span data-stu-id="04690-103">Either a component cannot find a directory named TEMP, or the drive or partition containing the TEMP directory lacks sufficient space to save information.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="04690-104">更正此错误</span><span class="sxs-lookup"><span data-stu-id="04690-104">To correct this error</span></span>  
  
1.  <span data-ttu-id="04690-105">创建一个名为“TEMP”目录，并将 TEMP 环境变量设置为它的路径。</span><span class="sxs-lookup"><span data-stu-id="04690-105">Create a directory named "TEMP" and set the TEMP environment variable equal to its path.</span></span>  
  
2.  <span data-ttu-id="04690-106">通过清除不必要的文件增加驱动器空间，或者在另一个分区上创建一个临时目录，然后将 TEMP 环境变量设置为它的路径。</span><span class="sxs-lookup"><span data-stu-id="04690-106">Make space on the drive by erasing unnecessary files, or create a TEMP directory on another partition and set the TEMP environment variable equal to its path.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04690-107">另请参阅</span><span class="sxs-lookup"><span data-stu-id="04690-107">See Also</span></span>  
 [<span data-ttu-id="04690-108">错误类型</span><span class="sxs-lookup"><span data-stu-id="04690-108">Error Types</span></span>](../../visual-basic/programming-guide/language-features/error-types.md)
