---
title: 剪贴板格式无效
ms.date: 07/20/2015
f1_keywords:
- vbrID460
ms.assetid: 71a4a045-65bb-417d-b3bd-99a9fa3c53f6
ms.openlocfilehash: eef16096b269902dbaca6a344abf4c5f6a504fb7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="clipboard-format-is-not-valid"></a>剪贴板格式无效
指定的剪贴板格式是与正在执行的方法不兼容。 此错误的可能原因包括：  
  
-   使用剪贴板的`GetText`或`SetText`以外的其他剪贴板格式的方法`vbCFText`或`vbCFLink`。  
  
-   使用剪贴板的`GetData`或`SetData`以外的其他剪贴板格式的方法`vbCFBitmap`， `vbCFDIB`，或`vbCFMetafile`。  
  
-   使用`DataObject``GetData`方法或`SetData`方法替换为已注册格式 (HC000-& HFFFF)，由 Microsoft Windows 保留的范围中的剪贴板格式时该剪贴板格式尚未注册与 Microsoft Windows 一起。  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
-   删除无效的格式，并指定一个有效。  
  
## <a name="see-also"></a>请参阅  
 [剪贴板：添加其他格式](/cpp/mfc/clipboard-adding-other-formats)
