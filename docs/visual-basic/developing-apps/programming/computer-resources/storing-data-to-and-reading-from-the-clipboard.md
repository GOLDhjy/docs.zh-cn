---
title: 将数据存储到剪贴板以及从剪贴板读取数据 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Clipboard, storing data to (My.Computer.Clipboard)
- Clipboard, reading from (My.Computer.Clipboard)
- Clipboard
- My.Computer.Clipboard object, tasks
- data [Visual Basic], Clipboard
- reading data, from Clipboard
ms.assetid: f690119a-4378-4f7d-b20e-d9377ef49496
ms.openlocfilehash: eb8ae25f260ed434c4aafcc064be8fb6bebaaac1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33591374"
---
# <a name="storing-data-to-and-reading-from-the-clipboard-visual-basic"></a>将数据存储到剪贴板以及从剪贴板读取数据 (Visual Basic)
剪贴板可用于存储文本和图像等数据。 由于所有活动进程都共享剪贴板，因此它可用于在这些活动进程之间传输数据。 使用 `My.Computer.Clipboard` 对象可轻松访问剪贴板并从中读取和向其写入数据。  
  
## <a name="reading-from-the-clipboard"></a>从剪贴板读取数据  
 使用 <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.GetText%2A> 方法读取剪贴板中的文本。 下面的代码读取文本并将其显示在消息框中。 剪贴板中必须存储文本该示例才能正常运行。  
  
 [!code-vb[VbVbcnMyClipboard#4](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/storing-data-to-and-reading-from-the-clipboard_1.vb)]  
  
 此代码示例也可作为 IntelliSense 代码片段。 在代码片段选取器中，它位于“Windows 窗体应用程序”>“剪贴板”中。 有关详细信息，请参阅[代码片段](/visualstudio/ide/code-snippets)。  
  
 使用 <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.GetImage%2A> 方法从剪贴板检索图像。 本示例先检查剪贴板中是否存在图像，然后再检索图像并将其分配给 `PictureBox1`。  
  
 [!code-vb[VbResourceTasks#16](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/storing-data-to-and-reading-from-the-clipboard_2.vb)]  
  
 此代码示例也可作为 IntelliSense 代码片段。 在代码片段选取器中，它位于“Windows 窗体应用程序”>“剪贴板”中。有关详细信息，请参阅[代码片段](/visualstudio/ide/code-snippets)。  
  
 即使在关闭应用程序后，剪贴板中存储的项仍将保留。  
  
## <a name="determining-the-type-of-file-stored-in-the-clipboard"></a>确定存储在剪贴板中的文件类型  
 剪贴板中的数据可以采用多种形式，如文本、音频文件或图像。 若要确定哪种文件位于剪贴板中，可以使用如 <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.ContainsAudio%2A>、<xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.ContainsFileDropList%2A>、<xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.ContainsImage%2A> 和 <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.ContainsText%2A> 的方法。 如果有想要检查的自定义格式，可以使用 <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.ContainsData%2A> 方法。  
  
 使用 `ContainsImage` 函数可确定剪贴板中的数据是否为图像。 下面的代码检查数据是否为图像并相应地进行报告。  
  
 [!code-vb[VbResourceTasks#13](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/storing-data-to-and-reading-from-the-clipboard_3.vb)]  
  
## <a name="clearing-the-clipboard"></a>清除剪贴板  
 <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.Clear%2A> 方法可以清除剪贴板。 由于剪贴板被其他进程共享，清除它可能会影响这些进程。  
  
 下面的代码演示如何使用 `Clear` 方法。  
  
 [!code-vb[VbVbcnMyClipboard#3](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/storing-data-to-and-reading-from-the-clipboard_4.vb)]  
  
## <a name="writing-to-the-clipboard"></a>写入剪贴板  
 使用 <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.SetText%2A> 方法将文本写入剪贴板。 下面的代码将字符串“This is a test string”写入剪贴板。  
  
 [!code-vb[VbVbcnMyClipboard#1](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/storing-data-to-and-reading-from-the-clipboard_5.vb)]  
  
 `SetText` 方法可接受包含 <xref:System.Windows.Forms.TextDataFormat> 类型的格式参数。 下面的代码可将字符串“This is a test string”以 RTF 文本格式写入剪贴板。  
  
 [!code-vb[VbVbcnMyClipboard#2](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/storing-data-to-and-reading-from-the-clipboard_6.vb)]  
  
 使用 <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.SetData%2A> 方法将数据写入剪贴板。 此示例将以自定义格式 `specialFormat` 向剪贴板写入 `DataObject``dataChunk`。  
  
 [!code-vb[VbVbcnMyClipboard#7](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/storing-data-to-and-reading-from-the-clipboard_7.vb)]  
  
 使用 <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.SetAudio%2A> 方法将音频数据写入剪贴板。 此示例将创建字节数组 `musicReader`，向其中读取文件 `cool.wav`，然后将其写入剪贴板。  
  
 [!code-vb[VbResourceTasks#5](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/storing-data-to-and-reading-from-the-clipboard_8.vb)]  
  
> [!IMPORTANT]
>  由于其他用户可访问剪贴板，不要将其用于存储密码或机密数据等敏感信息。  
  
## <a name="see-also"></a>请参阅  
 <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy>  
 <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.GetAudioStream%2A>  
 <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.SetDataObject%2A>  
 [如何：从 XML 文件中读取对象数据](../../../programming-guide/concepts/serialization/how-to-read-object-data-from-an-xml-file.md)  
 [如何：将对象数据写入 XML 文件](../../../programming-guide/concepts/serialization/how-to-write-object-data-to-an-xml-file.md)
