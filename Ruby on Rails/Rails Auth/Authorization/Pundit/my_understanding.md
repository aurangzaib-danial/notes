
# My Understanding
Every model has a policy model that contains all of their permissions. This makes it easier for me to define permissions specific to each model and be organized. Every policy model accepts an user and an object of the subject model.

A policy object is composed of an user and an active record object. This policy object can answer our questions of whether the user attached to it can perform certain actions on the active record object.

Pundit does not do anything I could not have done by myself. It is a very simple library. However, it is very pleasing that someone else has already made the design decisions for me which can be very difficult to make.
