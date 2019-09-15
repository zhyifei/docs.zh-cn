---
title: GetCustomUI
ms.date: 03/30/2017
helpviewer_keywords:
- custom error messages [WPF]
ms.assetid: e55180fc-35bb-4f80-a136-772b5eb3e4e5
ms.openlocfilehash: a9c4c9d597f5cc1b172213d49a3dd5b8f1c1f671
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/14/2019
ms.locfileid: "70991378"
---
# <a name="getcustomui"></a>GetCustomUI
由 Presentationhost.exe 调用，用于获取主机的自定义进度和错误消息（如果已实现）。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetCustomUI( [out] BSTR* pwzProgressAssemblyName, [out] BSTR* pwzProgressClassName, [out] BSTR* pwzErrorAssemblyName, [out] BSTR* pwzErrorClassName );  
```  
  
## <a name="parameters"></a>参数  
 `pwzProgressAssemblyName`  
  
 弄指向包含主机提供的进度用户界面的程序集的指针。  
  
 `pwzProgressClassName`  
  
 弄类的名称，它是宿主提供的进度用户界面，最好[!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)]是具有<xref:System.Windows.Controls.Page>的文件是顶级元素。 此类驻留在指定`pwzProgressAssemblyName`的程序集中。  
  
 `pwzErrorAssemblyName`  
  
 弄指向包含宿主提供的错误用户界面的程序集的指针。  
  
 `pwzErrorClassName`  
  
 弄类的名称，它是宿主提供的错误用户界面，最好是具有<xref:System.Windows.Controls.Page>的 XAML 文件是它的顶级元素。 此类驻留在指定`pwzErrorAssemblyName`的程序集中。  
  
## <a name="property-valuereturn-value"></a>属性值/返回值  
 HRESULT：已忽略。  
  
## <a name="remarks"></a>备注  
 宿主应用程序可能有 Presentationhost.exe 的默认用户界面不符合的特定主题。 如果是这种情况，主机应用程序可以实现[GetCustomUI](getcustomui.md) ，将进度和错误用户界面返回到 presentationhost.exe。 Presentationhost.exe 在使用其默认用户界面之前，将始终调用[GetCustomUI](getcustomui.md) 。  
  
 此函数在 Presentationhost.exe 的初始化过程中调用一次。  
  
## <a name="see-also"></a>请参阅

- [IWpfHostSupport](iwpfhostsupport.md)
