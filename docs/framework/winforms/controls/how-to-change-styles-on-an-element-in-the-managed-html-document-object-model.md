---
title: "如何：在托管 HTML 文档对象模型中更改元素的样式"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- managed HTML DOM [Windows Forms], changing styles on elements
ms.assetid: 154e8d9f-3e2d-4e8b-a6f3-c85a070e9cc1
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 3726ccdebf310d831fb0d7ea21fab011293f6d99
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-change-styles-on-an-element-in-the-managed-html-document-object-model"></a>如何：在托管 HTML 文档对象模型中更改元素的样式
你可以使用 HTML 中的样式来控制文档及其元素的外观。 <xref:System.Windows.Forms.HtmlDocument>和<xref:System.Windows.Forms.HtmlElement>支持<xref:System.Windows.Forms.HtmlElement.Style%2A>采用以下格式的样式字符串的属性：  
  
 `name1:value1;...;nameN:valueN;`  
  
 下面是`DIV`带设置为 Arial，所有的文本为加粗字体的样式字符串：  
  
 `<DIV style="font-face:arial;font-weight:bold;">`  
  
 `Hello, world!`  
  
 `</DIV>`  
  
 操作使用的样式的问题<xref:System.Windows.Forms.HtmlElement.Style%2A>属性是可证明难以将添加到和从字符串中移除单个样式设置。 例如，它将成为一个复杂的过程，每当用户将光标放置呈现上一个文本将以斜体显示的`DIV`，并当光标离开去掉斜体`DIV`。 如果你需要处理大量的这种方式中的样式，则时间将会成为问题。  
  
 下面的过程包含你可以使用能够轻松地处理 HTML 文档和元素的样式的代码。 过程要求你知道如何在 Windows 窗体，例如创建一个新项目并将控件添加到窗体中执行基本任务。  
  
### <a name="to-process-style-changes-in-a-windows-forms-application"></a>若要处理在 Windows 窗体应用程序中的样式更改  
  
1.  创建新的 Windows 窗体项目。  
  
2.  创建新的类文件以适合您的编程语言扩展名结尾。  
  
3.  复制`StyleGenerator`到类文件中，类本主题的示例部分中的代码，然后保存该代码。  
  
4.  将以下 HTML 保存到名为 Test.htm 的文件。  
  
    ```  
    <HTML>  
        <BODY>  
  
            <DIV style="font-face:arial;font-weight:bold;">  
                Hello, world!  
            </DIV><P>  
  
            <DIV>  
                Hello again, world!  
            </DIV><P>  
  
        </BODY>  
    </HTML>  
    ```  
  
5.  添加<xref:System.Windows.Forms.WebBrowser>控件名为`webBrowser1`到你的项目的主窗体。  
  
6.  将以下代码添加到你的项目的代码文件。  
  
    > [!IMPORTANT]
    >  确保`webBrowser1_DocumentCompleted`事件处理程序配置为侦听程序<xref:System.Windows.Forms.WebBrowser.DocumentCompleted>事件。 在[!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)]，双击<xref:System.Windows.Forms.WebBrowser>控制; 请在文本编辑器中，以编程方式配置侦听器。  
  
     [!code-csharp[ManagedDOMStyles#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ManagedDOMStyles/CS/Form1.cs#2)]
     [!code-vb[ManagedDOMStyles#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ManagedDOMStyles/VB/Form1.vb#2)]  
  
7.  运行该项目。 通过在第一个运行光标`DIV`以观察代码的影响。  
  
## <a name="example"></a>示例  
 下面的代码示例显示的完整代码`StyleGenerator`类，该类将现有的样式值的分析，支持添加、 更改，并移除样式，并返回一个新的样式值与请求的更改。  
  
 [!code-csharp[ManagedDOMStyles#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ManagedDOMStyles/CS/StyleGenerator.cs#1)]
 [!code-vb[ManagedDOMStyles#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ManagedDOMStyles/VB/StyleGenerator.vb#1)]  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Forms.HtmlElement>
