---
title: 如何：使用关键帧对颜色进行动画处理
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- colors [WPF], animating with key frames
- animation [WPF], colors with key frames
- key frames [WPF], animating colors with
ms.assetid: ab04ffa6-4de9-4d5b-a3b4-4e35d5b2ef35
ms.openlocfilehash: 7d89a1f9c24c93bd6b05265092bde09e8cf6eff5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33560327"
---
# <a name="how-to-animate-color-by-using-key-frames"></a>如何：使用关键帧对颜色进行动画处理
此示例演示如何进行动画处理<xref:System.Windows.Media.SolidColorBrush.Color%2A>的<xref:System.Windows.Media.SolidColorBrush>使用关键帧。  
  
## <a name="example"></a>示例  
 下面的示例使用<xref:System.Windows.Media.Animation.ColorAnimationUsingKeyFrames>类进行动画处理<xref:System.Windows.Media.SolidColorBrush.Color%2A>属性<xref:System.Windows.Media.SolidColorBrush>。 此动画按以下方式使用三个关键帧：  
  
1.  在第一个的两秒内，使用的是实例<xref:System.Windows.Media.Animation.LinearColorKeyFrame>类来从绿色到红色逐渐改变颜色。 之类的线性的关键帧<xref:System.Windows.Media.Animation.LinearColorKeyFrame>创建平滑的值之间的线性转换。  
  
2.  在下一步的末尾半秒，将使用的实例<xref:System.Windows.Media.Animation.DiscreteColorKeyFrame>类，以快速地将从红色的颜色更改为黄色。 之类的离散的关键帧<xref:System.Windows.Media.Animation.DiscreteColorKeyFrame>突变值，即，在动画的此部分的颜色更改快速发生的不是细微。  
  
3.  在最终的两秒内，使用的是实例<xref:System.Windows.Media.Animation.SplineColorKeyFrame>类重新更改颜色 — 这一次从黄色变回为绿色。 之类的样条关键帧<xref:System.Windows.Media.Animation.SplineColorKeyFrame>创建变量的值根据值之间转换<xref:System.Windows.Media.Animation.SplineColorKeyFrame.KeySpline%2A>属性。 在此示例中，颜色变化开始时缓慢，然后以指数方式加速，直到时间段结束。  
  
 [!code-csharp[keyframes_snip#ColorAnimationUsingKeyFramesWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/ColorAnimationUsingKeyFramesExample.cs#coloranimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#ColorAnimationUsingKeyFramesWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/coloranimationusingkeyframesexample.vb#coloranimationusingkeyframeswholepage)]
 [!code-xaml[keyframes_snip#ColorAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/ColorAnimationUsingKeyFramesExample.xaml#coloranimationusingkeyframeswholepage)]  
  
 有关完整示例，请参阅[关键帧动画示例](http://go.microsoft.com/fwlink/?LinkID=160012)。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Media.SolidColorBrush.Color%2A>  
 <xref:System.Windows.Media.SolidColorBrush>  
 <xref:System.Windows.Media.Animation.ColorAnimationUsingKeyFrames>  
 [关键帧动画概述](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [关键帧操作说明主题](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)
