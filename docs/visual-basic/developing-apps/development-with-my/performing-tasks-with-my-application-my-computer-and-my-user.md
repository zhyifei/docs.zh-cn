---
title: 使用 My.Application、My.Computer 和 My.User 执行任务
ms.date: 07/20/2015
helpviewer_keywords:
- My.Application object [Visual Basic], developing applications
- rapid application development (RAD), My.Application
- rapid application development (RAD), My.Computer
- rapid application development (RAD), My.User
- My.Computer object [Visual Basic], developing applications
- My.User object [Visual Basic], developing applications
ms.assetid: c8af61bd-4dd3-4a0f-9af5-795b594b240b
ms.openlocfilehash: fc9fd9093a3db4785bfc94719dbae9ec1d586050
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74329582"
---
# <a name="performing-tasks-with-myapplication-mycomputer-and-myuser-visual-basic"></a><span data-ttu-id="0f4c1-102">使用 My.Application、My.Computer 和 My.User 执行任务 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0f4c1-102">Performing Tasks with My.Application, My.Computer, and My.User (Visual Basic)</span></span>

<span data-ttu-id="0f4c1-103">提供访问信息和常用功能的三个中央 `My` 对象 `My.Application` （<xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>）、`My.Computer` （<xref:Microsoft.VisualBasic.Devices.Computer>）和 `My.User` （<xref:Microsoft.VisualBasic.ApplicationServices.User>）。</span><span class="sxs-lookup"><span data-stu-id="0f4c1-103">The three central `My` objects that provide access to information and commonly used functionality are `My.Application` (<xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>), `My.Computer` (<xref:Microsoft.VisualBasic.Devices.Computer>), and `My.User` (<xref:Microsoft.VisualBasic.ApplicationServices.User>).</span></span> <span data-ttu-id="0f4c1-104">你可以使用这些对象来访问与当前应用程序、安装了应用程序的计算机或应用程序的当前用户相关的信息。</span><span class="sxs-lookup"><span data-stu-id="0f4c1-104">You can use these objects to access information that is related to the current application, the computer that the application is installed on, or the current user of the application, respectively.</span></span>  
  
## <a name="myapplication-mycomputer-and-myuser"></a><span data-ttu-id="0f4c1-105">我的应用程序、计算机和用户</span><span class="sxs-lookup"><span data-stu-id="0f4c1-105">My.Application, My.Computer, and My.User</span></span>  

 <span data-ttu-id="0f4c1-106">下面的示例演示如何使用 `My`检索信息。</span><span class="sxs-lookup"><span data-stu-id="0f4c1-106">The following examples demonstrate how information can be retrieved using `My`.</span></span>  
  
 [!code-vb[VbVbcnMy#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMy/VB/Class1.vb#1)]  
  
 [!code-vb[VbVbcnMy#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMy/VB/Class1.vb#2)]  
  
 <span data-ttu-id="0f4c1-107">除了检索信息之外，通过这三个对象公开的成员还可以执行与该对象相关的方法。</span><span class="sxs-lookup"><span data-stu-id="0f4c1-107">In addition to retrieving information, the members exposed through these three objects also allow you to execute methods related to that object.</span></span> <span data-ttu-id="0f4c1-108">例如，你可以通过 `My.Computer`访问多种方法来操作文件或更新注册表。</span><span class="sxs-lookup"><span data-stu-id="0f4c1-108">For instance, you can access a variety of methods to manipulate files or update the registry through `My.Computer`.</span></span>  
  
 <span data-ttu-id="0f4c1-109">`My`（其中包含用于操作文件、目录和驱动器的各种方法和属性），使用文件 i/o 要大大简单快捷。</span><span class="sxs-lookup"><span data-stu-id="0f4c1-109">File I/O is significantly easier and faster with `My`, which includes a variety of methods and properties for manipulating files, directories, and drives.</span></span> <span data-ttu-id="0f4c1-110">使用 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser> 对象，您可以从具有分隔或固定宽度字段的大型结构化文件中进行读取。</span><span class="sxs-lookup"><span data-stu-id="0f4c1-110">The <xref:Microsoft.VisualBasic.FileIO.TextFieldParser> object allows you to read from large structured files that have delimited or fixed-width fields.</span></span> <span data-ttu-id="0f4c1-111">此示例将打开 `TextFieldParser` `reader` 并使用它从 `C:\TestFolder1\test1.txt`中读取。</span><span class="sxs-lookup"><span data-stu-id="0f4c1-111">This example opens the `TextFieldParser` `reader` and uses it to read from `C:\TestFolder1\test1.txt`.</span></span>  
  
 [!code-vb[VbVbalrTextFieldParser#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTextFieldParser/VB/Class1.vb#23)]  
  
 <span data-ttu-id="0f4c1-112">`My.Application` 使你可以更改应用程序的区域性。</span><span class="sxs-lookup"><span data-stu-id="0f4c1-112">`My.Application` allows you to change the culture for your application.</span></span> <span data-ttu-id="0f4c1-113">下面的示例演示如何调用此方法。</span><span class="sxs-lookup"><span data-stu-id="0f4c1-113">The following example demonstrates how this method can be called.</span></span>  
  
 [!code-vb[VbVbcnMy#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMy/VB/Class1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="0f4c1-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0f4c1-114">See also</span></span>

- <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>
- <xref:Microsoft.VisualBasic.Devices.Computer>
- <xref:Microsoft.VisualBasic.ApplicationServices.User>
- [<span data-ttu-id="0f4c1-115">My 对项目类型的依赖方式</span><span class="sxs-lookup"><span data-stu-id="0f4c1-115">How My Depends on Project Type</span></span>](../../../visual-basic/developing-apps/development-with-my/how-my-depends-on-project-type.md)
