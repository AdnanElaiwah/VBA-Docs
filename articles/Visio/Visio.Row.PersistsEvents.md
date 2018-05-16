---
title: Row.PersistsEvents Property (Visio)
keywords: vis_sdr.chm15814080
f1_keywords:
- vis_sdr.chm15814080
ms.prod: visio
api_name:
- Visio.Row.PersistsEvents
ms.assetid: a4bdb46e-9f9b-fdb7-3ab1-0e724b8d817f
ms.date: 06/08/2017
---


# Row.PersistsEvents Property (Visio)

Indicates whether an object is capable of containing persistent events in its  **EventList** collection. Read-only.


## Syntax

 _expression_ . **PersistsEvents**

 _expression_ A variable that represents a **Row** object.


### Return Value

Integer


## Remarks

Every object that has an  **EventList** property also has a **PersistsEvents** property. To be persistable, an event's action code must be **visActCodeRunAddon** , but it must also be in the **EventList** collection of an object whose **PersistsEvents** property is **True** . The only objects that currently persist events are **Document** , **Master** , and **Page** objects.

Whether a persistable event actually does persist depends on the value of its  **Persistent** property.


## Example

This Microsoft Visual Basic for Applications (VBA) macro shows how to use the  **PersistsEvents** property to determine if an object is capable of containing persistent events. Executing the macro prints 1 ( **True** ), 1 ( **True** ), and 0 ( **False** ) in the **Immediate** window for the **Document** , **Page** , and **Window** objects, respectively.


```vb
 
Public Sub PersistsEvents_Example() 
 
 Dim vsoDocument As Visio.Document 
 
 Set vsoDocument = Documents.Add("") 
 Debug.Print vsoDocument.PersistsEvents 
 Debug.Print ActivePage.PersistsEvents 
 Debug.Print ActiveWindow.PersistsEvents 
 
End Sub
```

