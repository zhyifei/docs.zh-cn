---
title: "XamlName 语法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- DottedXamlName grammar [XAML Services]
- grammar [XAML Services], DottedXamlName
- grammar [XAML Services], XamlName
- names in XAML [XAML Services]
- XamlName grammar [XAML Services]
ms.assetid: 11e4cada-41d2-494d-9531-0d3df4dfcbe3
caps.latest.revision: "13"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 47a2d72ea9558003412cc3773e26fb5be751fa19
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="xamlname-grammar"></a><span data-ttu-id="40b25-102">XamlName 语法</span><span class="sxs-lookup"><span data-stu-id="40b25-102">XamlName Grammar</span></span>
<span data-ttu-id="40b25-103">XamlName 语法是 XAML 语言规范 [MS-XAML]，这将为方便起见在此处重现中定义特定语法。</span><span class="sxs-lookup"><span data-stu-id="40b25-103">XamlName Grammar is a specific grammar that is defined in the XAML language specification [MS-XAML], which is reproduced here for convenience.</span></span>  
  
## <a name="from-the-xaml-specification"></a><span data-ttu-id="40b25-104">从 XAML 规范</span><span class="sxs-lookup"><span data-stu-id="40b25-104">From the XAML Specification</span></span>  
 <span data-ttu-id="40b25-105">[MS-XAML] 规范定义的语法 XamlName 来识别用于类型和属性的合法符号标识符的集。</span><span class="sxs-lookup"><span data-stu-id="40b25-105">The [MS-XAML] specification defines the grammar XamlName to identify the set of legal symbolic identifiers used for types and properties.</span></span>  
  
 <span data-ttu-id="40b25-106">字符串值的类型 XamlName 必须符合以下语法：</span><span class="sxs-lookup"><span data-stu-id="40b25-106">String values that are of type XamlName must conform to the following grammar:</span></span>  
  
```  
XamlName ::= NameStartChar ( NameChar )*   
NameStartChar ::= LetterCharacter | '_'   
NameChar ::= NameStartChar | DecimalDigit | CombiningCharacter   
LetterCharacter ::= UnicodeLu | UnicodeLl | UnicodeLo | UnicodeLt | UnicodeNl   
DecimalDigit ::= UnicodeNd   
CombiningCharacter ::= UnicodeMn | UnicodeMc  
```  
  
 <span data-ttu-id="40b25-107">在 Unicode 字符数据库中定义，这假定以下常规类别值</span><span class="sxs-lookup"><span data-stu-id="40b25-107">Which assumes the following general category values as defined in the Unicode Character Database</span></span>  
  
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
  
 <span data-ttu-id="40b25-108">XAML 定义第二个语法，DottedXamlName，用于属性和事件限定的引用，并还附加成员。</span><span class="sxs-lookup"><span data-stu-id="40b25-108">XAML defines a second grammar, DottedXamlName, that is used for property and event qualified references, and also for attached members.</span></span> <span data-ttu-id="40b25-109">有关详细信息，请参阅<xref:System.Windows.DependencyProperty>和[XAML 概述 (WPF)](../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)。</span><span class="sxs-lookup"><span data-stu-id="40b25-109">For more information, see <xref:System.Windows.DependencyProperty> and [XAML Overview (WPF)](../../../docs/framework/wpf/advanced/xaml-overview-wpf.md).</span></span>  
  
 <span data-ttu-id="40b25-110">字符串值的类型 DottedXamlName 必须符合以下语法：</span><span class="sxs-lookup"><span data-stu-id="40b25-110">String values that are of type DottedXamlName must conform to the following grammar:</span></span>  
  
```  
DottedXamlName ::= XamlName '.' XamlName  
```  
  
## <a name="remarks"></a><span data-ttu-id="40b25-111">备注</span><span class="sxs-lookup"><span data-stu-id="40b25-111">Remarks</span></span>  
 <span data-ttu-id="40b25-112">有关完整规范，请参阅[ \[MS-XAML\]](http://go.microsoft.com/fwlink/?LinkId=114525)。</span><span class="sxs-lookup"><span data-stu-id="40b25-112">For the complete specification, see [\[MS-XAML\]](http://go.microsoft.com/fwlink/?LinkId=114525).</span></span>
