---
title: "加载 DLL 时出错 (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vbrID48
ms.assetid: 4226cd1f-028c-477d-88a5-cb57f7e0cdc8
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: cc557dcc6709178b6519adb56f31debcbd1d1c39
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="error-in-loading-dll-visual-basic"></a>加载 DLL 时出错 (Visual Basic)
动态链接库 (DLL) 是中指定一个库`Lib`子句`Declare`语句。 此错误的可能原因包括：  
  
-   文件不是可执行的 DLL。  
  
-   文件不是 Microsoft Windows DLL。  
  
-   DLL 引用不存在的另一个 DLL。  
  
-   DLL 或引用的 DLL 不在路径中指定的目录。  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
-   如果源文本文件，因此不 DLL 的可执行文件，该文件，它必须为编译并链接到 DLL 的可执行文件窗体。  
  
-   如果文件不是 Microsoft Windows DLL，获取 Microsoft Windows 等效。  
  
-   如果 DLL 引用不存在的另一个 DLL，获取引用的 DLL 并使其可用。  
  
-   如果 DLL 或引用的 DLL 不是指定的路径的目录，请将 DLL 移动到引用的目录。  
  
## <a name="see-also"></a>另请参阅  
 [Declare 语句](../../../visual-basic/language-reference/statements/declare-statement.md)
