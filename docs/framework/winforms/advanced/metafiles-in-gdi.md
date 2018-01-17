---
title: "GDI+ 中的图元文件"
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
- images [Windows Forms], metafiles
- GDI+, metafiles
- metafiles
ms.assetid: 51da872c-c783-440f-8bf6-1e580a966c31
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2b9d378f82b2a7edca00fedaacdcc0fca179c5a0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="metafiles-in-gdi"></a>GDI+ 中的图元文件
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]提供<xref:System.Drawing.Imaging.Metafile>类，以便你可以录制和显示图元文件。 图元文件，也称为矢量图像，是存储为一系列绘图命令和设置的映像。 命令和设置记录在<xref:System.Drawing.Imaging.Metafile>可以存储在内存中对象，或将其保存到文件或流。  
  
## <a name="metafile-formats"></a>图元文件格式  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]可以显示已存储在以下格式的图元文件：  
  
-   Windows 图元文件 (WMF)  
  
-   增强型图元文件 (EMF)  
  
-   EMF +  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]可以记录图元文件中的 EMF 和 EMF + 格式中，但不是在 WMF 格式。  
  
 EMF + 是允许的 EMF 的扩展[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]要存储的记录。 有两种变体 EMF + 格式： EMF + 只有和 EMF + 双重。 EMF + 仅图元文件仅包含[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]记录。 此类图元文件可由显示[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]但不是[!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)]。 EMF + 双重图元文件包含[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]和[!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)]记录。 每个[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]记录中 EMF + 双重图元文件与配对备用[!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)]记录。 此类图元文件可由显示[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]或[!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)]。  
  
 下面的示例显示图元文件的以前保存为文件。 具有在其左上角显示图元文件 （100，100）。  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#21)]  
  
## <a name="see-also"></a>请参阅  
 [图像、位图和图元文件](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)
