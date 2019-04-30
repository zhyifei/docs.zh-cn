---
title: 参数 BasePath 必须是一个文件夹的路径
ms.date: 07/20/2015
ms.assetid: b180ce60-ad57-41a6-a313-491d86d84cc7
ms.openlocfilehash: 30f84bd1a903ae7c6e5e370cea3de0468091b9f7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61977179"
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
