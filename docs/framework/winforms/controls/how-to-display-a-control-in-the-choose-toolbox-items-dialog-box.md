---
title: 如何：在“选择工具箱项”对话框中显示控件
ms.date: 03/30/2017
helpviewer_keywords:
- global assembly cache [Windows Forms], Choose Toolbox Items dialog box
- AssemblyFoldersEx [Windows Forms], Choose Toolbox Items dialog box
- controls [Windows Forms], display in Choose Toolbox Items dialog box
- assembly folder registration [Windows Forms], Choose Toolbox Items dialog box
- Choose Toolbox Items dialog box [Windows Forms], display control
ms.assetid: 01ef6eba-d044-40f0-951d-78eff7ebd9a9
ms.openlocfilehash: fdda72d60b0f18e76b03e9b7f05060a09763a3f7
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/03/2018
ms.locfileid: "43488256"
---
# <a name="how-to-display-a-control-in-the-choose-toolbox-items-dialog-box"></a>如何：在“选择工具箱项”对话框中显示控件
在开发和分发控件，您可能希望出现在这些控件**选择工具箱项**对话框中，右键单击时显示**工具箱**，然后选择**选择项**。 可以使控件能够显示在此对话框中的使用 AssemblyFoldersEx 注册过程。  
  
### <a name="to-display-your-control-in-the-choose-toolbox-items-dialog-box"></a>若要在选择工具箱项对话框中显示控件  
  
-   在控件程序集安装到全局程序集缓存中。 有关详细信息，请参阅[如何： 将程序集安装到全局程序集缓存](../../../../docs/framework/app-domains/how-to-install-an-assembly-into-the-gac.md)  
  
     或  
  
-   使用 AssemblyFoldersEx 注册过程中注册您的控件和其关联的设计时程序集。 AssemblyFoldersEx 是框架的第三方供应商在其中存储每个版本，它们支持的路径的注册表位置。 设计时间解析度可以查看在此注册表位置，以查找引用程序集。 注册表脚本可以指定你想要显示在工具箱中的控件。 有关详细信息，请参阅[部署自定义控件和设计时程序集 (Visual Studio 2013)](https://msdn.microsoft.com/library/96158eb0-b691-4ae1-9e7b-3c65a1b798cb)。  
  
## <a name="see-also"></a>请参阅  
 [“选择工具箱项”对话框 (Visual Studio)](https://msdn.microsoft.com/library/bd07835f-18a8-433e-bccc-7141f65263bb)  
 [部署自定义控件和设计时程序集 (Visual Studio 2013)](https://msdn.microsoft.com/library/96158eb0-b691-4ae1-9e7b-3c65a1b798cb)  
 [设计时开发 Windows 窗体控件](../../../../docs/framework/winforms/controls/developing-windows-forms-controls-at-design-time.md)  
 [如何：将程序集安装到全局程序集缓存](../../../../docs/framework/app-domains/how-to-install-an-assembly-into-the-gac.md)  
 [演练：使用自定义组件自动填充工具箱](../../../../docs/framework/winforms/controls/walkthrough-automatically-populating-the-toolbox-with-custom-components.md)
