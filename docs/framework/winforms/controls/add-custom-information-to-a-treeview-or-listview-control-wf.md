---
title: 如何：向 TreeView 或 ListView 控件添加自定义信息
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- ListItem
helpviewer_keywords:
- examples [Windows Forms], TreeView control
- examples [Windows Forms], ListView control
- ListView control [Windows Forms], adding custom information
- TreeView control [Windows Forms], adding custom information
ms.assetid: 68be11de-1d5b-430e-901f-cfbe48d14b19
ms.openlocfilehash: fe507c41de97e9332f3f27e453a476d992f86627
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76732219"
---
# <a name="how-to-add-custom-information-to-a-treeview-or-listview-control-windows-forms"></a>방법: TreeView 또는 ListView 컨트롤에 사용자 지정 정보 추가(Windows Forms)
可以在 Windows 窗体 <xref:System.Windows.Forms.TreeView> 控件或 <xref:System.Windows.Forms.ListView> 控件中的派生项中创建派生节点。 파생은 필드를 처리하는 사용자 지정 메서드 및 생성자뿐만 아니라 필요로 하는 모든 필드를 추가할 수 있습니다. 이 기능을 사용하여 각 트리 노드 또는 목록 항목에 고객 개체를 연결합니다. 此处的示例针对 <xref:System.Windows.Forms.TreeView> 控件，但相同的方法可用于 <xref:System.Windows.Forms.ListView> 控件。  
  
### <a name="to-derive-a-tree-node"></a>트리 노드를 파생하려면  
  
- 创建一个新的 node 类，该类派生自 <xref:System.Windows.Forms.TreeNode> 类，该类具有一个用于记录文件路径的自定义字段。  
  
    ```vb  
    Class myTreeNode  
       Inherits TreeNode  
  
       Public FilePath As String  
  
       Sub New(ByVal fp As String)  
          MyBase.New()  
          FilePath = fp  
          Me.Text = fp.Substring(fp.LastIndexOf("\"))  
       End Sub  
    End Class  
    ```  
  
    ```csharp  
    class myTreeNode : TreeNode  
    {  
       public string FilePath;  
  
       public myTreeNode(string fp)  
       {  
          FilePath = fp;  
          this.Text = fp.Substring(fp.LastIndexOf("\\"));  
       }  
    }  
    ```  
  
    ```cpp  
    ref class myTreeNode : public TreeNode  
    {  
    public:  
       System::String ^ FilePath;  
  
       myTreeNode(System::String ^ fp)  
       {  
          FilePath = fp;  
          this->Text = fp->Substring(fp->LastIndexOf("\\"));  
       }  
    };  
    ```  
  
### <a name="to-use-a-derived-tree-node"></a>파생된 트리 노드를 사용하려면  
  
1. 함수 호출에 대한 매개 변수로 새롭게 파생된 트리 노드를 사용할 수 있습니다.  
  
     아래 예제에서 텍스트 파일의 위치에 설정된 경로는 내 문서 폴더입니다. Windows 운영 체제를 실행하는 대부분 컴퓨터가 이 디렉터리에 포함된다고 가정할 수 있기 때문에 그렇습니다. 또한 최소한의 시스템 액세스 수준을 가진 사용자가 안전하게 애플리케이션을 실행할 수 있습니다.  
  
    ```vb  
    ' You should replace the bold text file   
    ' in the sample below with a text file of your own choosing.  
    TreeView1.Nodes.Add(New myTreeNode (System.Environment.GetFolderPath _  
       (System.Environment.SpecialFolder.Personal) _  
       & "\ TextFile.txt ") )  
    ```  
  
    ```csharp  
    // You should replace the bold text file   
    // in the sample below with a text file of your own choosing.  
    // Note the escape character used (@) when specifying the path.  
    treeView1.Nodes.Add(new myTreeNode(System.Environment.GetFolderPath
       (System.Environment.SpecialFolder.Personal)
       + @"\TextFile.txt") );  
    ```  
  
    ```cpp  
    // You should replace the bold text file   
    // in the sample below with a text file of your own choosing.  
    treeView1->Nodes->Add(new myTreeNode(String::Concat(  
       System::Environment::GetFolderPath  
       (System::Environment::SpecialFolder::Personal),  
       "\\TextFile.txt")));  
    ```  
  
2. 如果传递的是树节点，并且它被类型化为 <xref:System.Windows.Forms.TreeNode> 类，则需要强制转换为派生类。 캐스팅은 개체의 한 유형에서 다른 유형으로의 명시적 변환입니다. 有关强制转换的详细信息，请参阅[隐式和显式转换](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)（Visual Basic）、[强制转换和类型转换](../../../csharp/programming-guide/types/casting-and-type-conversions.md)（视觉对象C#）或[强制转换运算符：（）](/cpp/cpp/cast-operator-parens) （视觉对象C++）。  
  
    ```vb  
    Public Sub TreeView1_AfterSelect(ByVal sender As Object, ByVal e As System.Windows.Forms.TreeViewEventArgs) Handles TreeView1.AfterSelect  
       Dim mynode As myTreeNode  
       mynode = CType(e.node, myTreeNode)  
       MessageBox.Show("Node selected is " & mynode.filepath)  
    End Sub  
    ```  
  
    ```csharp  
    protected void treeView1_AfterSelect (object sender,  
    System.Windows.Forms.TreeViewEventArgs e)  
    {  
       myTreeNode myNode = (myTreeNode)e.Node;  
       MessageBox.Show("Node selected is " + myNode.FilePath);  
    }  
    ```  
  
    ```cpp  
    private:  
       System::Void treeView1_AfterSelect(System::Object ^  sender,  
          System::Windows::Forms::TreeViewEventArgs ^  e)  
       {  
          myTreeNode ^ myNode = safe_cast<myTreeNode^>(e->Node);  
          MessageBox::Show(String::Concat("Node selected is ",   
             myNode->FilePath));  
       }  
    ```  
  
## <a name="see-also"></a>另请参阅

- [TreeView 컨트롤](treeview-control-windows-forms.md)
- [ListView 컨트롤](listview-control-windows-forms.md)
