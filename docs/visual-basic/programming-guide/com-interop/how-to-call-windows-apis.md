---
title: "如何：调用 Windows API (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- API calls [Visual Basic]
- Windows API, calling
- API calls [Visual Basic], platform invoke
- calls [Visual Basic], stored procedures
ms.assetid: 27d75f0a-54ab-4ee1-b91d-43513a19b12d
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a219e031cdd36c713db8dcee6cc1da3849c9cf93
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-call-windows-apis-visual-basic"></a>如何：调用 Windows API (Visual Basic)
此示例定义并调用`MessageBox`user32.dll 中的函数然后将字符串传递给它。  
  
## <a name="example"></a>示例  
 [!code-vb[VbVbalrInterop#1](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/how-to-call-windows-apis_1.vb)]  
  
## <a name="compiling-the-code"></a>编译代码  
 此示例需要：  
  
-   对 <xref:System> 命名空间的引用。  
  
## <a name="robust-programming"></a>可靠编程  
 以下情况可能会导致异常：  
  
-   该方法不是静态的是抽象的或之前已定义。 父类型是接口或长度*名称*或*dll 名称*为零。 (<xref:System.ArgumentException>)  
  
-   *名称*或*dll 名称*是`Nothing`。 (<xref:System.ArgumentNullException>)  
  
-   之前已使用 `CreateType` 创建包含类型。 (<xref:System.InvalidOperationException>)  
  
## <a name="see-also"></a>另请参阅  
 [详述平台调用](http://msdn.microsoft.com/en-us/ba9dd55b-2eaa-45cd-8afd-75cb8d64d243)  
 [平台调用示例](../../../framework/interop/platform-invoke-examples.md)  
 [使用非托管 DLL 函数](../../../framework/interop/consuming-unmanaged-dll-functions.md)  
 [定义一个方法使用反射发出](http://msdn.microsoft.com/en-us/84fd3bf6-628f-41aa-83d9-b990cf926e81)  
 [演练：调用 Windows API](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md)  
 [COM 互操作](../../../visual-basic/programming-guide/com-interop/index.md)
