---
title: "Events Overview"
description: "A brief overview about events with .NET Windows Forms."
ms.date: 04/02/2025
ms.service: dotnet-desktop
ms.topic: overview
dev_langs: ["csharp", "vb"]
helpviewer_keywords:
  - "Windows Forms, event handling"
  - "events [Windows Forms], about events"
  - "delegates [Windows Forms], multicast"
  - "delegates [Windows Forms], events and"
  - "multicast event delegates"
  - "Windows Forms controls, events"
---

# Events overview

An event is an action that you can respond to, or "handle," in code. Events are usually generated by a user action, such as clicking the mouse or pressing a key, but they can also be generated by program code or by the system.

Event-driven applications run code in response to an event. Each form and control exposes a predefined set of events that you can respond to. If one of these events is raised and there's an associated event handler, the handler is invoked and code is run.

The types of events raised by an object vary, but many types are common to most controls. For example, most objects have a <xref:System.Windows.Forms.Control.Click> event that's raised when a user clicks on it.

> [!NOTE]
> Many events occur with other events. For example, in the course of the <xref:System.Windows.Forms.Control.DoubleClick> event occurring, the <xref:System.Windows.Forms.Control.MouseDown>, <xref:System.Windows.Forms.Control.MouseUp>, and <xref:System.Windows.Forms.Control.Click> events occur.

For general information about how to raise and consume an event, see [Handling and raising events in .NET](/dotnet/standard/events/index).

## Delegates and their role

Delegates are classes commonly used within .NET to build event-handling mechanisms. Delegates roughly equate to function pointers, commonly used in Visual C++ and other object-oriented languages. Unlike function pointers however, delegates are object-oriented, type-safe, and secure. Also, where a function pointer contains only a reference to a particular function, a delegate consists of a reference to an object, and references to one or more methods within the object.

This event model uses *delegates* to bind events to the methods that are used to handle them. The delegate enables other classes to register for event notification by specifying a handler method. When the event occurs, the delegate calls the bound method. For more information about how to define delegates, see [Handling and raising events](/dotnet/standard/events/index).

Delegates can be bound to a single method or to multiple methods, referred to as multicasting. When creating a delegate for an event, you typically create a multicast event. A rare exception might be an event that results in a specific procedure (such as displaying a dialog box) that wouldn't logically repeat multiple times per event. For information about how to create a multicast delegate, see [How to combine delegates (Multicast Delegates)](/dotnet/csharp/programming-guide/delegates/how-to-combine-delegates-multicast-delegates).

A multicast delegate maintains an invocation list of the methods it's bound to. The multicast delegate supports a <xref:System.Delegate.Combine%2A> method to add a method to the invocation list and a <xref:System.Delegate.Remove%2A> method to remove it.

When an event is recorded by the application, the control raises the event by invoking the delegate for that event. The delegate in turn calls the bound method. In the most common case (a multicast delegate), the delegate calls each bound method in the invocation list in turn, which provides a one-to-many notification. This strategy means that the control doesn't need to maintain a list of target objects for event notification—the delegate handles all registration and notification.

Delegates also enable multiple events to be bound to the same method, allowing a many-to-one notification. For example, a button-click event and a menu-command–click event can both invoke the same delegate, which then calls a single method to handle these separate events the same way.

The binding mechanism used with delegates is dynamic: a delegate can be bound at run-time to any method whose signature matches that of the event handler. With this feature, you can set up or change the bound method depending on a condition and to dynamically attach an event handler to a control.

## Events in Windows Forms

Events in Windows Forms are declared with the <xref:System.EventHandler%601> delegate for handler methods. Each event handler provides two parameters that allow you to handle the event properly. The following example shows an event handler for a <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Click> event.

```vb
Private Sub button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles button1.Click

End Sub
```

```csharp
private void button1_Click(object sender, System.EventArgs e)
{

}
```

The first parameter,`sender`, provides a reference to the object that raised the event. The second parameter, `e`, passes an object specific to the event that's being handled. By referencing the object's properties (and, sometimes, its methods), you can obtain information such as the location of the mouse for mouse events or data being transferred in drag-and-drop events.

Typically each event produces an event handler with a different event-object type for the second parameter. Some event handlers, such as those for the <xref:System.Windows.Forms.Control.MouseDown> and <xref:System.Windows.Forms.Control.MouseUp> events, have the same object type for their second parameter. For these types of events, you can use the same event handler to handle both events.

You can also use the same event handler to handle the same event for different controls. For example, if you have a group of <xref:System.Windows.Forms.RadioButton> controls on a form, you could create a single event handler for the <xref:System.Windows.Forms.Control.Click> event of every `RadioButton`. For more information, see [How to handle a control event](../controls/how-to-add-an-event-handler.md#how-to-use-multiple-events-with-the-same-handler).

## Related content

- [Handling and raising events in .NET](/dotnet/standard/events/index)
- [How to handle a control event](../controls/how-to-add-an-event-handler.md)
