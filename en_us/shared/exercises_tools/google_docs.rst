.. _Google Document Tool:

#####################
Google Document Tool
#####################

This chapter describes how you can embed Google documents in your course. See:

* `Overview`_
* `Get the Google Document Embed Code`_
* `Enable Google Documents in edX Studio`_
* `Add a Google Document Component in edX Studio`_
* `Enable Google Documents in OLX`_
* `Add a Google Document Component in OLX`_

*********
Overview 
*********

You can embed a Google document in your course, so students see the document in
the courseware. For example, you can have students see a Google presentation:

.. image:: ../Images/google-presentation.png
  :alt: A Google presentation in courseware

You can embed the following types of Google documents:

* Document
* Presentation
* Spreadsheet
* Form
* Drawing

You must :ref:`get the Google document embed code<Get the Google Document Embed
Code>` to use the document in your course.

EdX Studio users then :ref:`enable<Enable Google Documents in edX Studio>` and
:ref:`add<Add a Google Document Component in edX Studio>` Google documents.

OLX users then :ref:`enable<Enable Google Documents in OLX>` and :ref:`add<Add
a Google Document Component in OLX>` Google documents.

You can also use :ref:`Google calendars<Google Calendar Tool>` in courseware.

.. _Get the Google Document Embed Code:

**********************************
Get the Google Document Embed Code
**********************************

Before you can add a Google document to your course, you must publish the
document to the web and get the embed code for the document.

#. Open the Google document.
#. From the **File** menu, select **Publish to the web**.
   
   .. image:: ../Images/google-publish-to-web.png
    :alt: The Google document Publish to web dialog box

#. Click **Publish**, then click **OK** to confirm.
#. Click the **Embed** tab.
      
   .. image:: ../Images/google-embed.png
    :alt: The Google document Publish to web Embed tab

#. Copy the complete string in the **Embed** field, including the `<iframe>`
   tags.

   You will use that string when configuring the Google document component.

.. _Enable Google Documents in edX Studio:

*************************************
Enable Google Documents in edX Studio
*************************************

To enable Google documents in your course, in edX Studio:

#. From the **Settings** menu, select **Advanced Settings**.
#. In the **Advanced Modules List**, add `google-document`. For example:
   
   .. image:: ../Images/google-advanced-setting.png
    :alt: Advanced modules setting for Google Documents

#. Click **Save Changes** at the bottom of the page.

.. _Add a Google Document Component in edX Studio:

******************************************************
Add a Google Document Component in edX Studio
******************************************************

Ensure you :ref:`enable Google documents<Enable Google Documents in edX
Studio>` before you add the component.

To add a Google document component:

#. In the unit where you want to create the component, under **Add New
   Component**, click the **Advanced**.

   .. image:: ../Images/google-components.png
    :alt: The Advanced component list with Google Document

#. Click **Google Document**.
   
   The new component is added to the unit, with the default Google presentation
   embedded.

   .. image:: ../Images/google-document-studio.png
    :alt: The Google document component in a Unit page

#. In the component that appears, click **Edit**.
   
   .. image:: ../Images/google-document-edit-studio.png
    :alt: The Google document editor

#. Modify the **Display Name** as needed.

#. In the **Embed Code** field, paste the embed code you copied in the task
   `Get the Google Document Embed Code`_.

#. Click **Save**.

.. _Enable Google Documents in OLX:

*******************************
Enable Google Documents in OLX
*******************************

To enable Google documents in your course, you must add the string `google-
document` to the `course` element's `advanced-modules` attribute in the XML
file that defines the course structure.

For example, the following XML file enables Google documents and calendars:

.. code-block:: xml

  <course advanced_modules="[&quot;google-document&quot;, 
      &quot;google-calendar&quot;]" display_name="Sample Course" 
      start="2014-01-01T00:00:00Z">
      ...
  </course>

For more information, see :ref:`The Courseware Structure`.

.. _Add a Google Document Component in OLX:

*******************************************
Add a Google Document Component in OLX
*******************************************