---
title: "如何：对区域使用命中测试"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hit tests [Windows Forms], using regions
- regions [Windows Forms], hit testing
ms.assetid: 3a4c07cb-a40a-4d14-ad35-008f531910a8
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7c0766c989df7c2329aa4d36af834378b02b1301
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-hit-testing-with-a-region"></a>如何：对区域使用命中测试
命中测试的目的是确定光标是否位于给定的对象，例如图标或按钮。  
  
## <a name="example"></a>示例  
 下面的示例通过两个矩形区域的并集创建形 plus 区域。 假定变量`point`包含最新的单击的位置。 代码将检查以查看是否`point`形 plus 区域中。 如果该点位于的区域 （命中），该区域是用不透明的红色画笔填充。 否则，该区域是用半透明的红色画笔填充。  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.MiscLegacyTopics#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a>编译代码  
 前面的示例专用于 Windows 窗体，它需要 <xref:System.Windows.Forms.PaintEventArgs> `e`，这是 <xref:System.Windows.Forms.PaintEventHandler> 的参数。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Drawing.Region>  
 [GDI+ 中的区域](../../../../docs/framework/winforms/advanced/regions-in-gdi.md)  
 [如何：对区域使用剪贴薄](../../../../docs/framework/winforms/advanced/how-to-use-clipping-with-a-region.md)
