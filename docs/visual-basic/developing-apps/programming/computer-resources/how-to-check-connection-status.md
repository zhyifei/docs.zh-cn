---
title: 如何：在 Visual Basic 中检查连接状态
ms.date: 07/20/2015
helpviewer_keywords:
- Web connections [Visual Basic]
- IsAvailable property [Visual Basic], about IsAvailable
- connections [Visual Basic], checking status
- connection status [Visual Basic]
ms.assetid: 4d9ee8ab-9a6f-4279-ace4-b75afc976a74
ms.openlocfilehash: 4a6cb67474d03ada5e0a73d94f65da7a381c44a8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33582459"
---
# <a name="how-to-check-connection-status-in-visual-basic"></a>如何：在 Visual Basic 中检查连接状态
<xref:Microsoft.VisualBasic.Devices.Network.IsAvailable> 属性可用于确定计算机是否具有有效的网络连接或 Internet 连接。  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-check-whether-a-computer-has-a-working-connection"></a>检查计算机是否具有有效的网络连接  
  
-   确定 `IsAvailable` 属性是 `True` 还是 `False`。 以下代码检查属性的状态并进行报告：  
  
     [!code-vb[VbResourceTasks#3](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-check-connection-status_1.vb)]  
  
     此代码示例也可作为 IntelliSense 代码片段。 它位于代码片段选取器的“连接和网络”中。 有关详细信息，请参阅[代码片段](/visualstudio/ide/code-snippets)。  
  
## <a name="see-also"></a>请参阅  
 <xref:Microsoft.VisualBasic.Devices.Network?displayProperty=nameWithType>  
 <xref:Microsoft.VisualBasic.Devices.Network.IsAvailable>
