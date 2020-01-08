---
title: 如何：调用 Windows API
ms.date: 07/20/2015
helpviewer_keywords:
- API calls [Visual Basic]
- Windows API, calling
- API calls [Visual Basic], platform invoke
- calls [Visual Basic], stored procedures
ms.assetid: 27d75f0a-54ab-4ee1-b91d-43513a19b12d
ms.openlocfilehash: 9de9f0fbcca291af0b6aadfd8e3fe7033708fbc6
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/25/2019
ms.locfileid: "75347535"
---
# <a name="how-to-call-windows-apis-visual-basic"></a>如何：调用 Windows API (Visual Basic)
此示例定义并调用 mscoree.dll 中的 `MessageBox` 函数，然后向其传递一个字符串。  
  
## <a name="example"></a>示例  
 [!code-vb[VbVbalrInterop#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#1)]  
  
## <a name="compile-the-code"></a>编译代码  
 此示例需要：  
  
- 对 <xref:System> 命名空间的引用。  
  
## <a name="robust-programming"></a>可靠的编程  
 以下情况可能会导致异常：  
  
- 方法不是静态的，也不是抽象的，或者以前定义过。 父类型为接口，或*name*或*dllName*的长度为零。 (<xref:System.ArgumentException>)  
  
- *名称*或*dllName* `Nothing`。 (<xref:System.ArgumentNullException>)  
  
- 之前已使用 `CreateType` 创建包含类型。 (<xref:System.InvalidOperationException>)  
  
## <a name="see-also"></a>另请参阅

- [平台调用详解](../../../framework/interop/consuming-unmanaged-dll-functions.md#a-closer-look-at-platform-invoke)
- [平台调用示例](../../../framework/interop/platform-invoke-examples.md)
- [使用非托管 DLL 函数](../../../framework/interop/consuming-unmanaged-dll-functions.md)
- [使用反射发出定义方法](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/w63y4d4f(v=vs.100))
- [演练：调用 Windows API](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md)
- [COM 互操作](../../../visual-basic/programming-guide/com-interop/index.md)
