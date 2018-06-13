---
title: 类型的值&#39; &lt;typename1&gt; &#39;不能转换为&#39; &lt;typename2&gt; &#39; （多个文件引用）
ms.date: 07/20/2015
f1_keywords:
- vbc30961
- bc30961
helpviewer_keywords:
- BC30961
ms.assetid: 8be5aa0d-d236-4ac3-aa9c-5044f9f6562b
ms.openlocfilehash: 41c18160be9b546f8b525376fa06bc0eca6c117a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33603686"
---
# <a name="value-of-type-39lttypename1gt39-cannot-be-converted-to-39lttypename2gt39-multiple-file-references"></a>类型的值&#39; &lt;typename1&gt; &#39;不能转换为&#39; &lt;typename2&gt; &#39; （多个文件引用）
类型的值\<typename1 > 不能转换为\<typename2 >。 类型不匹配可能是由于混合对的文件引用\<h 1 > 项目中\<projectname1 > 对的文件引用与\<h 2 > 项目中\<项目名称 2> >。 如果两个程序集完全相同，请尝试更换这些引用，以确保两个引用都来自相同的位置。  
  
 其中一个项目使多个文件引用的程序集的情况下，编译器不能保证一个类型可转换为另一个。  
  
 每个文件引用指定的文件路径和名称的项目 （通常为 DLL 文件） 的输出文件。 编译器无法保证输出文件来自同一源，或它们表示同一程序集的相同的版本。 因此，它不能保证不同的引用中的类型具有相同的类型，或甚至一个可以转换为其他。  
  
 如果你知道引用的程序集具有相同的程序集标识，你可以使用的单个文件引用。 *程序集标识* 包括程序集的名称、版本、公钥（如果有）和区域性。 此信息唯一地标识该程序集。  
  
 **错误 ID:** BC30961  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
-   如果被引用程序集具有相同的程序集标识，然后删除或替换其中的一个文件引用，以便只有单个文件引用。  
  
-   如果引用的程序集不具有相同的程序集标识，然后更改你的代码，以便它不会尝试转换到另一部分中的类型中的类型。  
  
## <a name="see-also"></a>请参阅  
 [在 Visual Basic 中的类型转换](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)  
 [管理项目中的引用](/visualstudio/ide/managing-references-in-a-project)  
 
