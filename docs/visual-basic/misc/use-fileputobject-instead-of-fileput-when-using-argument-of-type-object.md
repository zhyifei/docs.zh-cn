---
title: "使用 &#39;FilePutObject &#39;而不是 &#39;FilePut &#39;当使用自变量的类型和 #39; 对象 &#39;"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vbrUseFilePutObject
ms.assetid: d207b9b7-5898-4c13-8b03-9feefac5f726
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 8cba4af206e2dbf767fdb883ec81229a67842c57
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="use-39fileputobject39-instead-of-39fileput39-when-using-argument-of-type-39object39"></a>使用 &#39;FilePutObject &#39;而不是 &#39;FilePut &#39;当使用自变量的类型和 #39; 对象 &#39;
`FilePut`方法包含类型的自变量`Object`。 应使用`FilePutObject` 替代 `FilePut` ，以避免多义性。  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
-   将 `FilePut` 替换为 `FilePutObject`。  
  
-   将 `Object` 参数强制转换为一个更明确的类型。  
  
-   使用 `My.Computer.FileSystem` 对象中的可用功能。  
  
## <a name="see-also"></a>另请参阅  
 [不在生成中： FilePutObject 函数](http://msdn.microsoft.com/en-us/a0f52a1c-5ecc-4945-b18c-03147af61d6b)  
 [My.Computer.FileSystem 对象](../../visual-basic/language-reference/objects/my-computer-filesystem-object.md)  
 [My.Computer.FileSystem.WriteAllBytes 方法](http://msdn.microsoft.com/en-us/b1a24dc1-eac8-4e22-8ffa-cc3bacbaf826)
