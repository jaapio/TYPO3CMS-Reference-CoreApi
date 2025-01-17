.. include:: /Includes.rst.txt
.. index:: Events; AfterMailerInitializationEvent
.. _AfterMailerInitializationEvent:

==============================
AfterMailerInitializationEvent
==============================

This event is fired once a new Mailer is instantiated with specific transport settings.
So it is possible to add custom mailing settings.

Example
=======

An example listener, which hooks into the Mailer API to modify Mailer settings to not send any emails,
could look like this:

.. code-block:: php

   namespace MyCompany\MyPackage\EventListener;
   use TYPO3\CMS\Core\Mail\Event\AfterMailerInitializationEvent;

   final class NullMailer
   {
       public function __invoke(AfterMailerInitializationEvent $event): void
       {
           $event->getMailer()->injectMailSettings(['transport' => 'null']);
       }
   }

API
===

.. include:: /CodeSnippets/Events/Core/AfterMailerInitializationEvent.rst.txt
