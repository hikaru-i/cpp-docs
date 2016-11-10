---
title: "Using Custom Format Strings in a Date and Time Picker Control"
ms.custom: na
ms.date: "10/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDateTimeCtrl class, display styles"
  - "DateTimePicker control [MFC], display styles"
  - "DateTimePicker control [MFC]"
ms.assetid: 7d577f03-6ca0-4597-9093-50b78f304719
caps.latest.revision: 9
ms.author: "mblome"
manager: "ghogen"
translation.priority.ht: 
  - "cs-cz"
  - "de-de"
  - "es-es"
  - "fr-fr"
  - "it-it"
  - "ja-jp"
  - "ko-kr"
  - "pl-pl"
  - "pt-br"
  - "ru-ru"
  - "tr-tr"
  - "zh-cn"
  - "zh-tw"
---
# Using Custom Format Strings in a Date and Time Picker Control
By default, date and time picker controls provide three format types (each format corresponding to a unique style) for displaying the current date or time:  
  
-   **DTS_LONGDATEFORMAT** Displays the date in long format, producing output like "Wednesday, January 3, 2000".  
  
-   **DTS_SHORTDATEFORMAT** Displays the date in short format, producing output like "1/3/00".  
  
-   **DTS_TIMEFORMAT** Displays the time in long format, producing output like "5:31:42 PM".  
  
 However, you can customize the appearance of the date or time by using a custom format string. This custom string is made up of either existing format characters, nonformat characters, or a combination of both. Once the custom string is built, make a call to [CDateTimeCtrl::SetFormat](../Topic/CDateTimeCtrl::SetFormat.md) passing in your custom string. The date and time picker control will then display the current value using your custom format string.  
  
 The following example code (where `m_dtPicker` is the `CDateTimeCtrl` object) demonstrates one possible solution:  
  
 [!code[NVC_MFCControlLadenDialog#7](../mfc/codesnippet/CPP/using-custom-format-strings-in-a-date-and-time-picker-control_1.cpp)]  
  
 In addition to custom format strings, date and time picker controls also support [callback fields](../mfc/using-callback-fields-in-a-date-and-time-picker-control.md).  
  
## See Also  
 [Using CDateTimeCtrl](../mfc/using-cdatetimectrl.md)   
 [Controls](../mfc/controls--mfc-.md)