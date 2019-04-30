---
title: 参数 BasePath 必须是一个文件夹的路径
ms.date: 07/20/2015
ms.assetid: b180ce60-ad57-41a6-a313-491d86d84cc7
ms.openlocfilehash: 30f84bd1a903ae7c6e5e370cea3de0468091b9f7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61977179"
---
# <a name="argument-basepath-must-be-a-path-to-a-folder"></a><span data-ttu-id="7197a-102">参数 BasePath 必须是一个文件夹的路径</span><span class="sxs-lookup"><span data-stu-id="7197a-102">Argument BasePath must be a path to a folder</span></span>
<span data-ttu-id="7197a-103">参数 `BasePath` 必须包含文件夹的路径。</span><span class="sxs-lookup"><span data-stu-id="7197a-103">The argument `BasePath` must consist of a path to a folder.</span></span> <span data-ttu-id="7197a-104">你可能会错误地解析字符串，并提供一个未被识别为有效路径的值。</span><span class="sxs-lookup"><span data-stu-id="7197a-104">You may be parsing a string incorrectly and supplying a value that is not recognized as a valid path.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="7197a-105">更正此错误</span><span class="sxs-lookup"><span data-stu-id="7197a-105">To correct this error</span></span>  
  
- <span data-ttu-id="7197a-106">检查为 `BasePath` 提供的值，确保它是一个文件夹的有效路径。</span><span class="sxs-lookup"><span data-stu-id="7197a-106">Check the value you are supplying for `BasePath` to make sure it is a valid path to a folder.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7197a-107">请参阅</span><span class="sxs-lookup"><span data-stu-id="7197a-107">See also</span></span>

- <xref:System.CodeDom.Compiler.TempFileCollection.BasePath%2A>
- <xref:System.Resources.ResXResourceWriter.BasePath%2A>
- <xref:System.Resources.ResXResourceReader.BasePath%2A>
- [<span data-ttu-id="7197a-108">如何：分析文件路径</span><span class="sxs-lookup"><span data-stu-id="7197a-108">How to: Parse File Paths</span></span>](../../visual-basic/developing-apps/programming/drives-directories-files/how-to-parse-file-paths.md)
