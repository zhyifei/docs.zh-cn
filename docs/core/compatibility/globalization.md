---
title: 全球化中断性变更
description: 列出 .NET Core 中全球化过程内的中断性变更。
ms.date: 04/07/2020
ms.openlocfilehash: 1436f9e2ec540b0f8b1e710b25c2115646d4e5b4
ms.sourcegitcommit: 2b3b2d684259463ddfc76ad680e5e09fdc1984d2
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2020
ms.locfileid: "80888159"
---
# <a name="globalization-breaking-changes"></a><span data-ttu-id="5b9b8-103">全球化中断性变更</span><span class="sxs-lookup"><span data-stu-id="5b9b8-103">Globalization breaking changes</span></span>

<span data-ttu-id="5b9b8-104">本页记录了以下中断性变更：</span><span class="sxs-lookup"><span data-stu-id="5b9b8-104">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="5b9b8-105">重大更改</span><span class="sxs-lookup"><span data-stu-id="5b9b8-105">Breaking change</span></span> | <span data-ttu-id="5b9b8-106">引入的版本</span><span class="sxs-lookup"><span data-stu-id="5b9b8-106">Version introduced</span></span> |
| - | :-: |
| [<span data-ttu-id="5b9b8-107">StringInfo 和 TextElementEnumerator 现在与 UAX29 兼容</span><span class="sxs-lookup"><span data-stu-id="5b9b8-107">StringInfo and TextElementEnumerator are now UAX29-compliant</span></span>](#stringinfo-and-textelementenumerator-are-now-uax29-compliant) | <span data-ttu-id="5b9b8-108">5.0</span><span class="sxs-lookup"><span data-stu-id="5b9b8-108">5.0</span></span> |
| [<span data-ttu-id="5b9b8-109">“C”区域设置映射到固定区域设置</span><span class="sxs-lookup"><span data-stu-id="5b9b8-109">"C" locale maps to the invariant locale</span></span>](#c-locale-maps-to-the-invariant-locale) | <span data-ttu-id="5b9b8-110">3.0</span><span class="sxs-lookup"><span data-stu-id="5b9b8-110">3.0</span></span> |

## <a name="net-50"></a><span data-ttu-id="5b9b8-111">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="5b9b8-111">.NET 5.0</span></span>

[!INCLUDE [uax29-compliant-grapheme-enumeration](../../../includes/core-changes/globalization/5.0/uax29-compliant-grapheme-enumeration.md)]

***

## <a name="net-core-30"></a><span data-ttu-id="5b9b8-112">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="5b9b8-112">.NET Core 3.0</span></span>

[!INCLUDE["C" locale maps to the invariant locale](~/includes/core-changes/globalization/3.0/c-locale-maps-to-invariant-locale.md)]

***
