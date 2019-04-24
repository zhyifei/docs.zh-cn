---
title: <type1>'<typename>必须实现<methodname>for interface<interfacename>
ms.date: 07/20/2015
f1_keywords:
- vbc30149
- bc30149
helpviewer_keywords:
- BC30149
ms.assetid: 29d1b7f4-dca7-478c-bbe7-c657f342c183
ms.openlocfilehash: 432f089bc77928308820d7456d930fba8dc513f7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59304904"
---
# <a name="type1typename-must-implement-methodname-for-interface-interfacename"></a>\<类型 1 >\<类型名称 > 必须实现\<m h o d > 接口\<interfacename >
类或结构声明实现一个接口，但不实现的接口定义的过程。 必须实现该接口的每个成员。  
  
 **错误 ID:** BC30149  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
1. 声明具有相同名称和签名，因为在接口中定义的过程。 请务必包括至少`End Function`或`End Sub`语句。  
  
2. 添加`Implements`子句的末尾`Function`或`Sub`语句。 例如：  
  
    ```  
    Public Sub DoSomething() Implements IBaseInterface.DoSomething  
    ```  
  
## <a name="see-also"></a>请参阅

- [Implements 语句](../../../visual-basic/language-reference/statements/implements-statement.md)
- [接口](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
