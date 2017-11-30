---
title: "弱引用"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- weak references, short
- weak references, using
- weak references, long
- garbage collection, weak references
ms.assetid: 6a600fe5-3af3-4c64-82da-10a0a8e2d79b
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 906c23caa7065486bb094ad2475ed9e7e24b3d9c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="weak-references"></a>弱引用
如果应用程序的代码可以访问一个正由该程序使用的对象，垃圾回收器就不能回收该对象， 那么，就认为应用程序对该对象具有强引用。  
  
 弱引用允许应用程序访问对象，同时也允许垃圾回收器收集相应的对象。 如果不存在强引用，则弱引用的有限期只限于收集对象前的一个不确定的时间段。 使用弱引用时，应用程序仍可对该对象进行强引用，这样做可防止该对象被收集。 但始终存在这样的风险：垃圾回收器在重新建立强引用之前先处理该对象。  
  
 占用大量内存，但通过垃圾回收功能回收以后很容易重新创建的对象特别适合使用弱引用。  
  
 假设在 Windows 窗体应用程序中的树视图向用户显示复杂分层供选择的选项。 如果基础数据量很大，则用户使用应用程序中的其他部分时，在内存中保留该树会导致效率低下。  
  
 当用户离开切换到应用程序的另一部分时，你可以使用<xref:System.WeakReference>类来创建对树的弱引用和销毁所有强引用。 当用户切换回该树时，应用程序会尝试获得对该树的强引用，如果成功，就不必重新构造该树。  
  
 若要建立的对象的弱引用，你可以创建<xref:System.WeakReference>使用对象的实例进行跟踪。 然后将 <xref:System.WeakReference.Target%2A> 属性设置为该对象，将该对象的原始引用设置为 `null`。 有关代码示例，请参阅<xref:System.WeakReference>类库中。  
  
## <a name="short-and-long-weak-references"></a>短弱引用和长弱引用  
 可以创建短弱引用或长弱引用：  
  
-   Short  
  
     垃圾回收功能回收对象后，短弱引用的目标会变为 `null`。 弱引用本身是托管对象，与其他任何托管对象一样需要经过垃圾回收。  短的弱引用是默认构造函数<xref:System.WeakReference>。  
  
-   Long  
  
     一个长弱引用保留在对象之后<xref:System.Object.Finalize%2A>调用方法。 这样，便可以重新创建该对象，但该对象仍保持不可预知的状态。 若要使用的长的引用，指定`true`中<xref:System.WeakReference>构造函数。  
  
     如果该对象的类型不具有<xref:System.Object.Finalize%2A>方法，短弱引用功能适用和弱引用是有效的仅直到目标收集，该后可能会发生随时终结器运行。  
  
 若要创建的强引用，并再次使用该对象，强制转换<xref:System.WeakReference.Target%2A>属性<xref:System.WeakReference>到的对象类型。 如果<xref:System.WeakReference.Target%2A>属性返回`null`，该对象已收集; 否则为你可以继续使用该对象，因为应用程序已重新获得对它的强引用。  
  
## <a name="guidelines-for-using-weak-references"></a>使用弱引用的准则  
 仅在必要时使用长弱引用，因为在终结后对象的状态不可预知。  
  
 避免对小对象使用弱引用，因为指针本身可能和对象一样大，或者比对象还大。  
  
 避免将弱引用作为内存管理问题的自动解决方案， 而应开发一个有效的缓存策略来处理应用程序的对象。  
  
## <a name="see-also"></a>另请参阅  
 [垃圾回收](../../../docs/standard/garbage-collection/index.md)
