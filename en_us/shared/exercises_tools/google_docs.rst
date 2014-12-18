.. _Google Document Tool:

#####################
Google Document Tool
#####################

This chapter describes how to embed Google documents in your course. See:

* `Overview`_
* `Obtain the Google Document Embed Code`_
* `Enable Google Documents in edX Studio`_
* `Add a Google Document Component in edX Studio`_
* `Enable Google Documents in OLX`_
* `Add a Google Document XBlock in OLX`_
* `Editing Google Documents`_

*********
Overview 
*********

You can embed a Google document in your course so students see the document in
the courseware. For example, you can share a Google spreadsheet with students:

.. image:: ../Images/google-spreadsheet.png
  :width: 600
  :alt: A Google spreadsheet in courseware

You can embed the following types of Google documents:

* Document
* Presentation
* Spreadsheet
* Form
* Drawing
  
Embedding a Google document in your course has three steps:

#. `Obtain the Google Document Embed Code`_.

#. Using :ref:`Studio<Enable Google Documents in edX Studio>` or
   :ref:`OLX<Enable Google Documents in OLX>`, enable Google calendars in your
   course.

#. Using :ref:`Studio<Add a Google Document Component in edX Studio>` or
   :ref:`OLX<Add a Google Document XBlock in OLX>`, add the Google calendar to
   your course.

You can also use :ref:`Google calendars<Google Calendar Tool>` in courseware.

.. _Obtain the Google Document Embed Code:

*************************************
Obtain the Google Document Embed Code
*************************************

Before you can add a Google document to your course, you must publish the
document to the web and get the embed code for the document.

#. Open the Google document.
#. From the **File** menu, select **Publish to the web**.
   
   .. image:: ../Images/google-publish-to-web.png
    :alt: The Google document Publish to the web dialog box

#. Click **Publish**, then select **OK** to confirm.
#. Click the **Embed** tab.
      
   .. image:: ../Images/google-embed.png
    :alt: The Google document Publish to web Embed tab

#. Copy the complete string in the **Embed** field, including the ``<iframe>``
   tags.

   .. note::  
    Google images do not have an ``<iframe>`` tag. You just copy the complete
    ``img`` tag.

   You will use that string to configure the Google document component.

.. _Enable Google Documents in edX Studio:

*************************************
Enable Google Documents in edX Studio
*************************************

To enable Google documents in your course:

#. From the **Settings** menu, select **Advanced Settings**.
#. In the **Advanced Module List** field, place your cursor between the braces,
   and then type ``"google-document"``. If you see other values in this field,
   add a comma after the closing quotation mark for the last value, and then
   type ``"google-document"``. For example:
   
   .. image:: ../Images/google-advanced-setting.png
    :alt: Advanced modules setting for Google documents

#. At the bottom of the page, select **Save Changes**.

.. _Add a Google Document Component in edX Studio:

******************************************************
Add a Google Document Component in edX Studio
******************************************************

Ensure you :ref:`enable Google documents<Enable Google Documents in edX
Studio>` before you add the component.

To add a Google document component:

#. In the unit where you want to create the component, under **Add New
   Component**, select **Advanced**.

   .. image:: ../Images/google-components.png
    :alt: The advanced component list with Google document

#. Click **Google Document**.
   
   The new component is added to the unit, with the default Google presentation
   embedded.

   .. image:: ../Images/google-document-studio.png
    :alt: The Google document component in a unit page

#. In the new component, select **Edit**.
   
   .. image:: ../Images/google-document-edit-studio.png
    :alt: The Google document editor

#. In the **Display Name** field, type the name for the component.

#. In the **Embed Code** field, paste the embed code you copied in the 
   `Obtain the Google Document Embed Code`_ task.

#. Click **Save**.

.. _Enable Google Documents in OLX:

*******************************
Enable Google Documents in OLX
*******************************

To enable Google documents in your course, you must add the string ``google-
document`` to the ``course`` element's ``advanced-modules`` attribute in the
XML file that defines the course structure.

For example, the following XML enables Google documents and calendars:

.. code-block:: xml

  <course advanced_modules="[&quot;google-document&quot;, 
      &quot;google-calendar&quot;]" display_name="Sample Course" 
      start="2014-01-01T00:00:00Z">
      ...
  </course>

For more information, see :ref:`The Courseware Structure`.

.. _Add a Google Document XBlock in OLX:

*******************************************
Add a Google Document XBlock in OLX
*******************************************

To add a Google document XBlock in OLX, you create the ``google-
document``element. You can embed the ``google-document`` element in the
``vertical`` element, or you can create the ``google-document`` element as a
stand-alone file that you reference in the vertical.

For more information, see :ref:`The Courseware Structure`.

For example:

.. code-block:: xml

  <google-document url_name="c5804436419148f68e2ee44abd396b12"
    embed_code="&lt;iframe width=&quot;500&quot; height=&quot;300&quot;
    frameborder=&quot;0&quot; src=&quot;https://docs.google.com/spreadsheet/pub
    ?key=0AuZ_5O2JZpH5dGVUVDNGUE05aTFNcEl2Z0ZuTUNmWUE&amp;output=html&amp;widge
    t=true&quot;&gt;&lt;/iframe&gt;" display_name="Google Document"/>

The value of the ``embed_code`` attribute is the embed code you copied in the
`Obtain the Google Document Embed Code`_ task.

.. note:: 
  The edX Learning Management System sets the height and width values for
  Google documents. If you change these values, the LMS overrides your changes.

**************************
Editing Google Documents
**************************

When you edit and save a Google document, the changes are automatically
reflected in the component. You do not need to edit the component. Students
will see the updated Google document.