---
title: "使用 &#39;FilePutObject &#39;而不是 &#39;FilePut &#39;当使用自变量的类型和 #39; 对象 &#39;"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrUseFilePutObject
ms.assetid: d207b9b7-5898-4c13-8b03-9feefac5f726
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 5612c2bd4dc08f767643d2cd865a2ba1a8210c15
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="use-39fileputobject39-instead-of-39fileput39-when-using-argument-of-type-39object39"></a>使用 &#39;FilePutObject &#39;而不是 &#39;FilePut &#39;当使用自变量的类型和 #39; 对象 &#39;
`FilePut`方法包含类型的自变量`Object`。 应使用`FilePutObject` 替代 `FilePut` ，以避免多义性。  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
-   将 `FilePut` 替换为 `FilePutObject`。  
  
-   将 `Object` 参数强制转换为一个更明确的类型。  
  
-   使用 `My.Computer.FileSystem` 对象中的可用功能。  
  
## <a name="see-also"></a>请参阅  
   
 [My.Computer.FileSystem](xref:Microsoft.VisualBasic.FileIO.FileSystem)  
 [My.Computer.FileSystem.WriteAllBytes](xref:Microsoft.VisualBasic.MyServices.FileSystemProxy.WriteAllBytes%2A)
