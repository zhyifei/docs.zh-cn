---
title: 剪贴板格式无效
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrID460
ms.assetid: 71a4a045-65bb-417d-b3bd-99a9fa3c53f6
caps.latest.revision: 10
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 0e7adc417d962de35272319d7dc976b237c7e2b6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="clipboard-format-is-not-valid"></a>剪贴板格式无效
指定的剪贴板格式是与正在执行的方法不兼容。 此错误的可能原因包括：  
  
-   使用剪贴板的`GetText`或`SetText`以外的其他剪贴板格式的方法`vbCFText`或`vbCFLink`。  
  
-   使用剪贴板的`GetData`或`SetData`以外的其他剪贴板格式的方法`vbCFBitmap`， `vbCFDIB`，或`vbCFMetafile`。  
  
-   使用`DataObject``GetData`方法或`SetData`方法替换为已注册格式 (HC000-& HFFFF)，由 Microsoft Windows 保留的范围中的剪贴板格式时该剪贴板格式尚未注册与 Microsoft Windows 一起。  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
-   删除无效的格式，并指定一个有效。  
  
## <a name="see-also"></a>另请参阅  
 [剪贴板：添加其他格式](/cpp/mfc/clipboard-adding-other-formats)
