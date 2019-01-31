---
title: 如何：在 Visual Basic 中检索“我的文档”目录中的内容
ms.date: 07/20/2015
helpviewer_keywords:
- My Documents directory
ms.assetid: 26560d01-7dda-4457-8e95-21db23d71aea
ms.openlocfilehash: 6313ebd190a6cee8a697399e2e77b63d8c43db2e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54602580"
---
# <a name="how-to-retrieve-the-contents-of-the-my-documents-directory-in-visual-basic"></a><span data-ttu-id="8ead5-102">如何：在 Visual Basic 中检索“我的文档”目录中的内容</span><span class="sxs-lookup"><span data-stu-id="8ead5-102">How to: Retrieve the Contents of the My Documents Directory in Visual Basic</span></span>
<span data-ttu-id="8ead5-103">可以使用 <xref:Microsoft.VisualBasic.FileIO.SpecialDirectories> 对象读取许多“所有用户”目录，例如“我的文档”或“桌面”。</span><span class="sxs-lookup"><span data-stu-id="8ead5-103">The <xref:Microsoft.VisualBasic.FileIO.SpecialDirectories> object can be used to read from many of the **All Users** directories, such as **My Documents** or **Desktop**.</span></span>  
  
### <a name="to-read-from-the-my-documents-folder"></a><span data-ttu-id="8ead5-104">读取“我的文档”文件夹</span><span class="sxs-lookup"><span data-stu-id="8ead5-104">To read from the My Documents folder</span></span>  
  
-   <span data-ttu-id="8ead5-105">可以使用 `ReadAllText`方法从特定目录中的每个文件中读取文本。</span><span class="sxs-lookup"><span data-stu-id="8ead5-105">Use the `ReadAllText` method to read the text from each file in a specific directory.</span></span> <span data-ttu-id="8ead5-106">以下代码指定一个目录和文件，然后使用 `ReadAllText` 将它们读入名为 `patients` 的字符串。</span><span class="sxs-lookup"><span data-stu-id="8ead5-106">The following code specifies a directory and file and then uses `ReadAllText` to read them into the string named `patients`.</span></span>  
  
     [!code-vb[VbVbcnMyFileSystem#15](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-retrieve-the-contents-of-the-my-documents-directory_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="8ead5-107">请参阅</span><span class="sxs-lookup"><span data-stu-id="8ead5-107">See also</span></span>
- <xref:Microsoft.VisualBasic.FileIO.SpecialDirectories>
- <xref:Microsoft.VisualBasic.FileIO.FileSystem.ReadAllText%2A>
