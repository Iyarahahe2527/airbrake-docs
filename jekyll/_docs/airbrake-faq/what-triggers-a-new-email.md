---
layout: classic-docs
title: What triggers a new notification
categories: [airbrake-faq]
---

Airbrake will send you a new notification for a new error or for new
occurrence of an error previously marked as resolved. When an error comes in,
we review information about the error to determine whether the error is a new
error entirely, or just another occurrence of an error we've previously seen.
We currently review...

- The error class of the error
- The error message of the error with data values extracted
(see [structured logging](/docs/features/structured-logging))
- The file in which the error occurred
- The line number at which the error occurred
- The `RAILS_ENV` that was set when the error occurred

## What is a notification?
A notification can be:

- Your personal email notifications
- Your team's messaging (eg: Slack) notifications
- Or your project's webhook integration if enabled

## Resolved notices

If you **resolve an error group** from within the application, don't worry --
if it comes in again, we'll "unresolve" it, and send you another notification
to indicate that it's been reopened. This is part of the benefit and purpose
behind the resolved feature. You should be able to remove from your immediate
view anything you believe is dealt with, but have the confidence to know that
you'll see it again if it's actually not done with, or it comes up again in the
future because of further changes.

To cut down on noise, Airbrake will not send you a new email notification for
an error if you have already received an email for that error less than one
minute ago.

## Error severity

Errors with a [severity](/docs/airbrake-faq/what-is-severity) of `debug`,
`info`, `notice`, or `warning` will not trigger a notification.

## High volume notifications

If you have enabled high volume notifications for your project you will be
re-notified when an error's occurrences reach 10k, 100k, 200k, 300k, etc.
High volume notifications can be enabled per project on your [user
profile](https://airbrake.io/users/notifications). High volume notifications help you keep
tabs on which errors occur most in your project, and depending on frequency
can be a useful indicator for larger issues.

High volume notifications are available on the [Business plan and above](https://airbrake.io/account/plan/edit).
