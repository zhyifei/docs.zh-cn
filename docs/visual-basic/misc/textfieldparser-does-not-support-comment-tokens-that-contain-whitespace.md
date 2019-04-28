---
title: TextFieldParser 不支持包含空格的注释标记
ms.date: 07/20/2015
f1_keywords:
- vbrTextFieldParser_WhitespaceInToken
ms.assetid: 55107656-270e-4bbb-841a-478904df8e07
ms.openlocfilehash: 9a14bc29ecfa917b6213f32cd170aa83d6f60f58
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61668986"
---
# <a name="textfieldparser-does-not-support-comment-tokens-that-contain-white-space"></a><span data-ttu-id="88fa0-102">TextFieldParser 不支持包含空格的注释标记</span><span class="sxs-lookup"><span data-stu-id="88fa0-102">TextFieldParser does not support comment tokens that contain white space</span></span>
<span data-ttu-id="88fa0-103">提供了包含空格的注释标记。</span><span class="sxs-lookup"><span data-stu-id="88fa0-103">A comment token that contains white space has been supplied.</span></span> <span data-ttu-id="88fa0-104">`TextFieldParser` 不支持包含空格的注释标记，除非空格出现在标记的开头。</span><span class="sxs-lookup"><span data-stu-id="88fa0-104">The `TextFieldParser` does not support comment tokens that contain white space unless the white space occurs at the beginning of the token.</span></span> <span data-ttu-id="88fa0-105">出现在标记开头的空格将被忽略。</span><span class="sxs-lookup"><span data-stu-id="88fa0-105">White space occurring at the beginning of a token is ignored.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="88fa0-106">更正此错误</span><span class="sxs-lookup"><span data-stu-id="88fa0-106">To correct this error</span></span>  
  
- <span data-ttu-id="88fa0-107">提供正确的注释标记。</span><span class="sxs-lookup"><span data-stu-id="88fa0-107">Supply a correct comment token.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88fa0-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="88fa0-108">See also</span></span>

- [<span data-ttu-id="88fa0-109">TextFieldParser.CommentTokens 属性</span><span class="sxs-lookup"><span data-stu-id="88fa0-109">TextFieldParser.CommentTokens Property</span></span>](xref:Microsoft.VisualBasic.FileIO.TextFieldParser.CommentTokens%2A)
- [<span data-ttu-id="88fa0-110">使用 TextFieldParser 对象分析文本文件</span><span class="sxs-lookup"><span data-stu-id="88fa0-110">Parsing Text Files with the TextFieldParser Object</span></span>](../../visual-basic/developing-apps/programming/drives-directories-files/parsing-text-files-with-the-textfieldparser-object.md)
- [<span data-ttu-id="88fa0-111">TextFieldParser 对象</span><span class="sxs-lookup"><span data-stu-id="88fa0-111">TextFieldParser Object</span></span>](../../visual-basic/language-reference/objects/textfieldparser-object.md)
