---
title: OpenFileDialog 组件概述（Windows 窗体）
ms.date: 03/30/2017
f1_keywords:
- OpenFileDialog
helpviewer_keywords:
- OpenFileDialog component [Windows Forms], about OpenFileDialog
- Open File dialog box [Windows Forms], displaying in Windows Forms
ms.assetid: cd717300-46b6-4f82-8207-b218fa7fa407
ms.openlocfilehash: 24327ded50ac927642e2687b40b1f10de9bdf41e
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211705"
---
# <a name="openfiledialog-component-overview-windows-forms"></a><span data-ttu-id="f4cc5-102">OpenFileDialog 组件概述（Windows 窗体）</span><span class="sxs-lookup"><span data-stu-id="f4cc5-102">OpenFileDialog Component Overview (Windows Forms)</span></span>

<span data-ttu-id="f4cc5-103">Windows 窗体 <xref:System.Windows.Forms.OpenFileDialog> 组件是一个预配置的对话框。</span><span class="sxs-lookup"><span data-stu-id="f4cc5-103">The Windows Forms <xref:System.Windows.Forms.OpenFileDialog> component is a pre-configured dialog box.</span></span> <span data-ttu-id="f4cc5-104">它是相同**打开的文件**公开的 Windows 操作系统的对话框。</span><span class="sxs-lookup"><span data-stu-id="f4cc5-104">It is the same **Open File** dialog box exposed by the Windows operating system.</span></span> <span data-ttu-id="f4cc5-105">它继承自 <xref:System.Windows.Forms.CommonDialog> 类。</span><span class="sxs-lookup"><span data-stu-id="f4cc5-105">It inherits from the <xref:System.Windows.Forms.CommonDialog> class.</span></span>

## <a name="use-this-component"></a><span data-ttu-id="f4cc5-106">使用此组件</span><span class="sxs-lookup"><span data-stu-id="f4cc5-106">Use this component</span></span>

<span data-ttu-id="f4cc5-107">将在基于 Windows 的应用程序中的此组件作为一个简单的解决方案的文件选择而不用配置你自己的对话框。</span><span class="sxs-lookup"><span data-stu-id="f4cc5-107">Use this component within your Windows-based application as a simple solution for file selection in lieu of configuring your own dialog box.</span></span> <span data-ttu-id="f4cc5-108">利用标准的 Windows 对话框，你可以创建其基本功能可立即为用户所熟悉的应用程序。</span><span class="sxs-lookup"><span data-stu-id="f4cc5-108">By relying on standard Windows dialog boxes, you create applications whose basic functionality is immediately familiar to users.</span></span> <span data-ttu-id="f4cc5-109">但是，应注意，当使用<xref:System.Windows.Forms.OpenFileDialog>组件，您必须编写您自己的文件打开逻辑。</span><span class="sxs-lookup"><span data-stu-id="f4cc5-109">Be aware, however, that when using the <xref:System.Windows.Forms.OpenFileDialog> component, you must write your own file-opening logic.</span></span>

<span data-ttu-id="f4cc5-110">使用<xref:System.Windows.Forms.CommonDialog.ShowDialog%2A>方法，以便在运行时显示对话框。</span><span class="sxs-lookup"><span data-stu-id="f4cc5-110">Use the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method to display the dialog at run time.</span></span> <span data-ttu-id="f4cc5-111">可以让用户选择多个文件与要打开<xref:System.Windows.Forms.OpenFileDialog.Multiselect%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="f4cc5-111">You can enable users to multi-select files to be opened with the <xref:System.Windows.Forms.OpenFileDialog.Multiselect%2A> property.</span></span> <span data-ttu-id="f4cc5-112">此外，还可以使用<xref:System.Windows.Forms.OpenFileDialog.ShowReadOnly%2A>属性来确定是否在对话框中显示只读复选框。</span><span class="sxs-lookup"><span data-stu-id="f4cc5-112">Additionally, you can use the <xref:System.Windows.Forms.OpenFileDialog.ShowReadOnly%2A> property to determine if a read-only check box appears in the dialog box.</span></span> <span data-ttu-id="f4cc5-113"><xref:System.Windows.Forms.OpenFileDialog.ReadOnlyChecked%2A>属性指示是否选定只读复选框。</span><span class="sxs-lookup"><span data-stu-id="f4cc5-113">The <xref:System.Windows.Forms.OpenFileDialog.ReadOnlyChecked%2A> property indicates whether the read-only check box is selected.</span></span> <span data-ttu-id="f4cc5-114">最后，<xref:System.Windows.Forms.FileDialog.Filter%2A>属性设置的当前文件名筛选器字符串，它确定在对话框中的"文件类型"框中显示的选项。</span><span class="sxs-lookup"><span data-stu-id="f4cc5-114">Finally, the <xref:System.Windows.Forms.FileDialog.Filter%2A> property sets the current file name filter string, which determines the choices that appear in the "Files of type" box in the dialog box.</span></span>

<span data-ttu-id="f4cc5-115">添加到窗体时<xref:System.Windows.Forms.OpenFileDialog>组件在 Visual Studio 中的 Windows 窗体设计器底部的任务栏中显示。</span><span class="sxs-lookup"><span data-stu-id="f4cc5-115">When it is added to a form, the <xref:System.Windows.Forms.OpenFileDialog> component appears in the tray at the bottom of the Windows Forms Designer in Visual Studio.</span></span>

## <a name="see-also"></a><span data-ttu-id="f4cc5-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="f4cc5-116">See also</span></span>

- <xref:System.Windows.Forms.OpenFileDialog>
- [<span data-ttu-id="f4cc5-117">OpenFileDialog 组件</span><span class="sxs-lookup"><span data-stu-id="f4cc5-117">OpenFileDialog Component</span></span>](openfiledialog-component-windows-forms.md)
