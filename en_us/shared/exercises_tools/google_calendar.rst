.. _Google Calendar Tool:

#####################
Google Calendar Tool
#####################

This chapter describes how to embed Google calendars in your course. See:

* `Overview`_
* `Obtain the Google Calendar ID`_
* `Enable Google Calendars in edX Studio`_
* `Add a Google Calendar Component in edX Studio`_
* `Enable Google Documents in OLX`_
* `Add a Google Calendar XBlock in OLX`_
* `Editing Google Calendars`_

*********
Overview 
*********

You can embed a Google calendar in your course so students see the calendar in
the courseware. You can use a Google calendar to share quiz dates, office
hours, or other schedules of interest to students. For example:

.. image:: ../Images/google-calendar.png
  :alt: A Google calendar in courseware

You must :ref:`get the Google calendar ID<Obtain the Google Calendar
ID>` to use the calendar in your course.

If you are using edX Studio, :ref:`enable<Enable Google Calendars in edX
Studio>` and :ref:`add<Add a Google Calendar Component in edX Studio>` Google
calendars.

If you are using OLX, then :ref:`enable<Enable Google Documents in OLX>` and
:ref:`add<Add a Google Calendar XBlock in OLX>` Google calendars.

You can also use :ref:`Google documents<Google Document Tool>` in courseware.

.. _Obtain the Google Calendar ID:

*************************************
Obtain the Google Calendar ID
*************************************

Before you can add a Google calendar to your course, you must make the calendar
public and get its embed code.

#. Open the Google calendar.
#. From the **Settings** menu, select **Settings**.
#. Select the **Calendars** tab.
   
   Your settings may list multiple calendars.  Find the calendar you want to
   share in your courseware.

#. In the row for the calendar to share, in the **SHARING** column, select
   **Edit Settings**.
#. In the Calendar Details page, check **Share this calender with others**.
#. Check **Make this calendar public**.
   
  .. image:: ../Images/google-calendar-settings.png
   :alt: Google calendar settings

7. Select **Save** and confirm the selection.
   
   You return the the calendar list.

#. Again, select **Edit Settings** for the calendar.
#. Select the **Calendar Details** tab.
#. Next to the **Calendar Address** label, select **HTML**.
   
   The Calendar Address dialog box opens, with a public web address for the
   calendar.

#. Copy the value of the ``src`` attribute from the address.
   
   .. note:: Do not copy the ``=`` character.

   .. image:: ../Images/google-calendar-address.png
    :alt: The Google calendar embed code

   You will use this value to configure the Google calendar component.

.. _Enable Google Calendars in edX Studio:

*************************************
Enable Google Calendars in edX Studio
*************************************

To enable Google calendars in your course, in edX Studio:

#. From the **Settings** menu, select **Advanced Settings**.
#. In the **Advanced Module List**, add ``google-calendar``. For example:
   
   .. image:: ../Images/google-advanced-setting.png
    :alt: Advanced modules setting for Google documents

#. At the bottom of the page, select **Save Changes**.

.. _Add a Google Calendar Component in edX Studio:

******************************************************
Add a Google Calendar Component in edX Studio
******************************************************

Ensure you :ref:`enable Google calendars<Enable Google Calendars in edX
Studio>` before you add the component.

To add a Google calendar component:

#. In the unit where you want to create the component, under **Add New
   Component**, select **Advanced**.

   .. image:: ../Images/google-components.png
    :alt: The Advanced component list with Google Calendar

#. Select **Google Calendar**.
   
   The new component is added to the unit, with the default Google calendar
   embedded.

   .. image:: ../Images/google-calendar-studio.png
    :alt: The Google calendar component in a unit page

#. In the new component, select **Edit**.
   
   .. image:: ../Images/google-calendar-edit.png
    :alt: The Google calendar editor

#. In the **Display Name** field, type the name for the component.

#. In the **Public Calendar ID** field, paste the calendar ID you copied in the
   `Obtain the Google Calendar ID`_ task.

#. For the **Default View** field, select **Month**, **Week**, or **Agenda**.
   
   This is the initial view students have the calendar. Each student can change
   his or her view.

#. Select **Save**.

.. _Enable Google Documents in OLX:

*******************************
Enable Google Documents in OLX
*******************************

To enable Google documents in your course, you must add the string ``google-calendar`` to the ``course`` element's ``advanced-modules`` attribute in the
XML file that defines the course structure.

For example, the following XML snippet enables Google documents and calendars:

.. code-block:: xml

  <course advanced_modules="[&quot;google-document&quot;, 
      &quot;google-calendar&quot;]" display_name="Sample Course" 
      start="2014-01-01T00:00:00Z">
      ...
  </course>

For more information, see :ref:`The Courseware Structure`.

.. _Add a Google Calendar XBlock in OLX:

*******************************************
Add a Google Calendar XBlock in OLX
*******************************************

To add a Google calendar XBlock in OLX, you create the ``google-calendar``
element, either embedded in the ``vertical`` element, or in its own file that
is referenced within the vertical. For more information, see :ref:`The
Courseware Structure`.

For example:

.. code-block:: xml

  <google-calendar url_name="4115e717366045eaae7764b2e1f25e4c" 
    calendar_id="instructor@univ.edu&amp;ctz=America/New_York" 
    default_view="1" display_name="Class Schedule"/>



The value of the ``calendar`` attribute is the calendar ID you copied in the
`Obtain the Google Calendar ID`_ task.

**************************
Editing Google Calendars
**************************

When you edit and save a Google calendar, the changes are automatically
reflected in the component. You do not need to edit the component. Students
will see the updated Google calendar.