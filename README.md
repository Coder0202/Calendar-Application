# Calendar-Application
🔹 OVERVIEW
program is made of two main parts:

CalendarApplication class – The main GUI window using Java Swing.

Event class – A model class that represents an individual calendar event.

🔹 CLASS: CalendarApplication (extends JFrame)
This is the main class and the graphical user interface (GUI) for the application.

🔸 Fields:
List<Event> events – Stores all the events.

JList<Event> eventList – A Swing component to display the list of events.

DefaultListModel<Event> listModel – Used by JList to hold the actual event items.

JButton addButton, editButton, deleteButton – Buttons for user interaction.

🔸 main() Method:
java
Copy
Edit
SwingUtilities.invokeLater(() -> new CalendarApplication().setVisible(true));
Starts the GUI on the Event Dispatch Thread (standard practice in Swing).

🔸 Constructor:
java
Copy
Edit
public CalendarApplication()
Sets window title, close operation, size, and calls initComponents() to set up the UI.

🔸 Method: initComponents()
Initializes all GUI components:

Creates the JList, buttons, and a panel for controls.

Adds the event list to the center of the frame and the buttons to the bottom.

Adds ActionListeners to handle button clicks for adding, editing, and deleting events.

🔸 Method: createNewEvent()
Prompts the user to enter:

Event name

Date (in yyyy-MM-dd format)

If input is valid:

Parses the date string into a Date object.

Creates a new Event and returns it.

If invalid input, shows an error dialog.

🔸 Method: editEvent(Event event)
Prompts the user to update the name and date of the selected event.

If valid input is given, updates the event's name and date.

If the date format is wrong, shows an error dialog.

🔸 Method: updateEventList()
Clears and refreshes the JList (eventList) by re-adding all events from the events list.

🔹 CLASS: Event
A simple class to represent an event with a name and date.

🔸 Fields:
String name – Event name.

Date date – Event date.

🔸 Constructor:
java
Copy
Edit
public Event(String name, Date date)
Initializes the name and date for the event.

🔸 Getters and Setters:
getName(), setName(String)

getDate(), setDate(Date)

🔸 Method: getDateStr()
Converts the Date to a String in "yyyy-MM-dd" format for display.

🔸 Method: toString()
java
Copy
Edit
@Override
public String toString() {
    return "Event: " + name + " Date: " + getDateStr();
}
Used to display each event in the JList as a formatted string.



