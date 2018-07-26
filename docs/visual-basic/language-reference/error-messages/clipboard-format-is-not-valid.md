---
title: 剪贴板格式无效
ms.date: 07/20/2015
f1_keywords:
- vbrID460
ms.assetid: 71a4a045-65bb-417d-b3bd-99a9fa3c53f6
ms.openlocfilehash: f2a0ab33c1749117d5de4987e85c44602ccd29ce
ms.sourcegitcommit: 70c76a12449439bac0f7a359866be5a0311ce960
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/25/2018
ms.locfileid: "39245552"
---
# <a name="clipboard-format-is-not-valid"></a>剪贴板格式无效
指定的剪贴板格式，与正在执行的方法不兼容。 此错误的可能原因是：  
  
-   使用剪贴板`GetText`或`SetText`剪贴板格式以外的其他方法`vbCFText`或`vbCFLink`。  
  
-   使用剪贴板`GetData`或`SetData`剪贴板格式以外的其他方法`vbCFBitmap`， `vbCFDIB`，或`vbCFMetafile`。  
  
-   使用`GetData`或`SetData`方法的`DataObject`与已注册的格式 （HC000-& HFFFF），由 Microsoft Windows 保留的范围中的剪贴板格式时该剪贴板格式尚未注册与 Microsoft Windows.  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
-   删除无效的格式，并指定一个有效。  
  
## <a name="see-also"></a>请参阅  
 [剪贴板：添加其他格式](/cpp/mfc/clipboard-adding-other-formats)
