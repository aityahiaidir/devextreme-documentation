---
id: dxScheduler.Options.recurrenceEditMode
type: Enums.RecurrenceEditMode
default: 'dialog'
---
---
##### shortDescription
Specifies the edit mode for recurring appointments.

---
This property accepts the following values:

- *"series"*  
 Enables a user to edit only entire appointment series.

- *"occurrence"*  
 Enables a user to edit only individual appointment instances.

- *"dialog"*   
 Displays a dialog that suggests a user to choose between editing the entire series or only the individual instance.

#include common-demobutton with {
    url: "https://js.devexpress.com/Demos/WidgetsGallery/Demo/Scheduler/RecurringAppointments/"
}

The Scheduler handles changes made to an instance and a series differently. If a user edits a recurring appointment instance, two actions are performed on the data objects:

- The series' data object is updated.
The Scheduler updates the field specified by [recurrenceExceptionExpr](/api-reference/10%20UI%20Components/dxScheduler/1%20Configuration/recurrenceExceptionExpr.md '/Documentation/ApiReference/UI_Components/dxScheduler/Configuration/#recurrenceExceptionExpr'), thus adding the edited instance to exceptions. The [onAppointmentUpdating](/api-reference/10%20UI%20Components/dxScheduler/1%20Configuration/onAppointmentUpdating.md '/Documentation/ApiReference/UI_Components/dxScheduler/Configuration/#onAppointmentUpdating') and [onAppointmentUpdated](/api-reference/10%20UI%20Components/dxScheduler/1%20Configuration/onAppointmentUpdated.md '/Documentation/ApiReference/UI_Components/dxScheduler/Configuration/#onAppointmentUpdated') event handlers are executed.

- A new data object is created.
This object contains the edited instance's data. The [onAppointmentAdding](/api-reference/10%20UI%20Components/dxScheduler/1%20Configuration/onAppointmentAdding.md '/Documentation/ApiReference/UI_Components/dxScheduler/Configuration/#onAppointmentAdding') and [onAppointmentAdded](/api-reference/10%20UI%20Components/dxScheduler/1%20Configuration/onAppointmentAdded.md '/Documentation/ApiReference/UI_Components/dxScheduler/Configuration/#onAppointmentAdded') event handlers are executed.

When a user deletes an instance, the Scheduler adds it to series' exceptions by updating the field specified in **recurrenceExceptionExpr**. Because this is an update, the **onAppointmentUpdating** and **onAppointmentUpdated** event handlers are executed instead of [onAppointmentDeleting](/api-reference/10%20UI%20Components/dxScheduler/1%20Configuration/onAppointmentDeleting.md '/Documentation/ApiReference/UI_Components/dxScheduler/Configuration/#onAppointmentDeleting') and [onAppointmentDeleted](/api-reference/10%20UI%20Components/dxScheduler/1%20Configuration/onAppointmentDeleted.md '/Documentation/ApiReference/UI_Components/dxScheduler/Configuration/#onAppointmentDeleted').

If a user edits a whole series, only the series data object is updated. When a whole series is deleted, its object is removed.
