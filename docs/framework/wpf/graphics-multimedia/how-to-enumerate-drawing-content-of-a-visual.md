---
title: 如何：枚举 Visual 的绘图内容
ms.date: 03/30/2017
helpviewer_keywords:
- retrieving the DrawingGroup value of a Visual [WPF]
- enumerating the contents of a Visual [WPF]
ms.assetid: 2974ddb3-2997-4713-8fd2-e93d549c58a8
ms.openlocfilehash: 19c37ec7df3542eb46b182f4790059eb16fef90b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-enumerate-drawing-content-of-a-visual"></a>如何：枚举 Visual 的绘图内容
<xref:System.Windows.Media.Drawing>对象提供的对象模型，用于枚举的内容<xref:System.Windows.Media.Visual>。  
  
## <a name="example"></a>示例  
 下面的示例使用<xref:System.Windows.Media.VisualTreeHelper.GetDrawing%2A>方法来检索<xref:System.Windows.Media.DrawingGroup>值<xref:System.Windows.Media.Visual>并枚举该值。  
  
> [!NOTE]
>  当你枚举视觉对象的内容时，就在检索<xref:System.Windows.Media.Drawing>对象，且不基础数据的表示形式呈现为向量图形指令列表。 有关详细信息，请参阅 [WPF 图形呈现概述](../../../../docs/framework/wpf/graphics-multimedia/wpf-graphics-rendering-overview.md)。  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMRetrieveDrawings](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/EnumerateDrawingsExample.xaml.cs#graphicsmmretrievedrawings)]  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Media.Drawing>  
 <xref:System.Windows.Media.DrawingGroup>  
 <xref:System.Windows.Media.VisualTreeHelper>  
 [Drawing 对象概述](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)  
 [WPF 图形呈现概述](../../../../docs/framework/wpf/graphics-multimedia/wpf-graphics-rendering-overview.md)
