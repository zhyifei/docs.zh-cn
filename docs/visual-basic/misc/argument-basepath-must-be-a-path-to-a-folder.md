---
title: 参数 BasePath 必须是一个文件夹的路径
ms.date: 07/20/2015
ms.assetid: b180ce60-ad57-41a6-a313-491d86d84cc7
ms.openlocfilehash: 9c15e2a7135ef3453e514735f7091097eeaa96c6
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "64659118"
---
# <a name="argument-basepath-must-be-a-path-to-a-folder"></a>参数 BasePath 必须是一个文件夹的路径
参数 `BasePath` 必须包含文件夹的路径。 你可能会错误地解析字符串，并提供一个未被识别为有效路径的值。  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
- 检查为 `BasePath` 提供的值，确保它是一个文件夹的有效路径。  
  
## <a name="see-also"></a>请参阅

- <xref:System.CodeDom.Compiler.TempFileCollection.BasePath%2A>
- <xref:System.Resources.ResXResourceWriter.BasePath%2A>
- <xref:System.Resources.ResXResourceReader.BasePath%2A>
- [如何：分析文件路径](../../visual-basic/developing-apps/programming/drives-directories-files/how-to-parse-file-paths.md)
