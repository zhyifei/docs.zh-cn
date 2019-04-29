---
title: XamlName 语法
ms.date: 03/30/2017
helpviewer_keywords:
- DottedXamlName grammar [XAML Services]
- grammar [XAML Services], DottedXamlName
- grammar [XAML Services], XamlName
- names in XAML [XAML Services]
- XamlName grammar [XAML Services]
ms.assetid: 11e4cada-41d2-494d-9531-0d3df4dfcbe3
ms.openlocfilehash: 642ca16142bdfe78a40ddf4e6a3a79ce6a8a4985
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61938744"
---
# <a name="xamlname-grammar"></a><span data-ttu-id="e4a06-102">XamlName 语法</span><span class="sxs-lookup"><span data-stu-id="e4a06-102">XamlName Grammar</span></span>
<span data-ttu-id="e4a06-103">XamlName 语法是为了方便起见，此处重现的 XAML 语言规范 [MS-XAML] 中定义的特定语法。</span><span class="sxs-lookup"><span data-stu-id="e4a06-103">XamlName Grammar is a specific grammar that is defined in the XAML language specification [MS-XAML], which is reproduced here for convenience.</span></span>  
  
## <a name="from-the-xaml-specification"></a><span data-ttu-id="e4a06-104">从 XAML 规范</span><span class="sxs-lookup"><span data-stu-id="e4a06-104">From the XAML Specification</span></span>  
 <span data-ttu-id="e4a06-105">[MS-XAML] 规范定义语法 XamlName 来标识用于类型和属性的合法符号标识符的集。</span><span class="sxs-lookup"><span data-stu-id="e4a06-105">The [MS-XAML] specification defines the grammar XamlName to identify the set of legal symbolic identifiers used for types and properties.</span></span>  
  
 <span data-ttu-id="e4a06-106">字符串值的类型 XamlName 必须符合以下语法：</span><span class="sxs-lookup"><span data-stu-id="e4a06-106">String values that are of type XamlName must conform to the following grammar:</span></span>  
  
```  
XamlName ::= NameStartChar ( NameChar )*   
NameStartChar ::= LetterCharacter | '_'   
NameChar ::= NameStartChar | DecimalDigit | CombiningCharacter   
LetterCharacter ::= UnicodeLu | UnicodeLl | UnicodeLo | UnicodeLt | UnicodeNl   
DecimalDigit ::= UnicodeNd   
CombiningCharacter ::= UnicodeMn | UnicodeMc  
```  
  
 <span data-ttu-id="e4a06-107">这假定以下常规类别值为 Unicode 字符数据库中定义</span><span class="sxs-lookup"><span data-stu-id="e4a06-107">Which assumes the following general category values as defined in the Unicode Character Database</span></span>  
  
```  
Lu  
Letter, Uppercase  
Ll  
Letter, Lowercase  
Lt  
Letter, Titlecase  
Lm  
Letter, Modifier  
Lo  
Letter, Other  
Mn  
Mark, Non-Spacing  
Mc  
Mark, Spacing Combining  
Nd  
Number, Decimal  
Nl  
Number, Letter  
```  
  
 <span data-ttu-id="e4a06-108">XAML 定义的第二个语法，DottedXamlName，是用于属性和事件限定的引用，并还为附加成员。</span><span class="sxs-lookup"><span data-stu-id="e4a06-108">XAML defines a second grammar, DottedXamlName, that is used for property and event qualified references, and also for attached members.</span></span> <span data-ttu-id="e4a06-109">有关详细信息，请参阅<xref:System.Windows.DependencyProperty>并[XAML 概述 (WPF)](../wpf/advanced/xaml-overview-wpf.md)。</span><span class="sxs-lookup"><span data-stu-id="e4a06-109">For more information, see <xref:System.Windows.DependencyProperty> and [XAML Overview (WPF)](../wpf/advanced/xaml-overview-wpf.md).</span></span>  
  
 <span data-ttu-id="e4a06-110">字符串值的类型 DottedXamlName 必须符合以下语法：</span><span class="sxs-lookup"><span data-stu-id="e4a06-110">String values that are of type DottedXamlName must conform to the following grammar:</span></span>  
  
```  
DottedXamlName ::= XamlName '.' XamlName  
```  
  
## <a name="remarks"></a><span data-ttu-id="e4a06-111">备注</span><span class="sxs-lookup"><span data-stu-id="e4a06-111">Remarks</span></span>  
 <span data-ttu-id="e4a06-112">有关完整规范，请参见[ \[MS XAML\]](https://go.microsoft.com/fwlink/?LinkId=114525)。</span><span class="sxs-lookup"><span data-stu-id="e4a06-112">For the complete specification, see [\[MS-XAML\]](https://go.microsoft.com/fwlink/?LinkId=114525).</span></span>
