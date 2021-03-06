---
title: "StyleExpr Property"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2018"
ms.assetid: 6400d515-9f4e-4422-a89e-99100bf9110c
caps.latest.revision: 18
manager: edupont
---
# StyleExpr Property
Specifies the format of text in a field. For fields in a **CueGroup** control, this property is used to configure the color of the color indicator on the cue.  

> [!NOTE]  
>  This note pertains to backward compatibility only. If the property is set to Boolean **true** or **false**, it sets whether the format specified in the [Style Property](Style-Property.md) property is applied to text in a field.  

## Applies To  

-   Page field controls that are not of data type Boolean or BLOB.  

-   Field controls in **CueGroups** of data type Boolean, Text, or Codeunit.  

## Property Value
You can set **StyleExpr** property to either the name of a variable; a text constant in apostrophes, for example, 'strong'; or, for backward compatibility, to **true** or **false**. 

|Value|Description|  
|-----|---------------|
|true|Applies the style that is specified by the **Style** property. |
|false|Does not apply the style that is specified by the **Style** property. This is the default value.|
|*Variable*|The variable can evaluate to **true** or **false**, or one of the following values (without apostrophes). If it evaluates to **true**, it applies the style that is specified by the **Style** property. |
|'standard'|Normal weight and color|  
|'standardaccent'|Normal weight, blue color|
|'strong'|Bold, normal color|  
|'strongaccent'|Bold, blue color| 
|'attention'|Italic, red color|  
|'attentionaccent'|Italic, blue color| 
|'favorable'|Bold, green color|Green|  
|'unfavorable'|Bold, italic, red color|  
|'ambiguous'|Normal weight, yellow color|  
|'subordinate'|Normal weight, gray color|  

> [!IMPORTANT]  
> **StyleExpr** must not be set to a Text or Boolean array; otherwise, it will compile, but fail at runtime.

## Remarks  
The information in this article is mainly applicable to formatting the text of page fields. For information about how to use the **StyleExpr** property for configuring Cues, see [How to: Set Up Colored Indicators on Cues by Using the Style and StyleExpr Property](How-to--Set-Up-Colored-Indicators-on-Cues-by-Using-the-Style-and-StyleExpr-Property.md).   

You can use a conditional setting of styles by inserting the conditional code in, for example, the [OnAfterGetRecord Trigger](OnAfterGetRecord-Trigger.md). Remember to cover all cases in `else` branches to avoid incorrect styles. For example: `if (MyField = 'abc') then   MyStyleVar := 'Ambiguous' else   MyStyleVar := 'Favorable'`.  

> [!IMPORTANT]  
>  To use a variable for the **StyleExpr** property, the [IncludeInDataSet Property](IncludeInDataSet-Property.md) of the variable must be set to **Yes**. 

 ## See Also  
 [How to: Style Field Text on a Page](How-to--Style-Field-Text-on-a-Page.md)
