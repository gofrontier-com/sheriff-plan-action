.. image:: https://github.com/gofrontier-com/sheriff-azure-devops-extension/actions/workflows/ci.yml/badge.svg
    :target: https://github.com/gofrontier-com/sheriff-azure-devops-extension/actions/workflows/ci.yml
.. image:: https://github.com/gofrontier-com/sheriff-azure-devops-extension/actions/workflows/release.yml/badge.svg
    :target: https://github.com/gofrontier-com/sheriff-azure-devops-extension/actions/workflows/release.yml

|

.. image:: images/extension-icon.png
  :width: 200
  :alt: Sheriff logo
  :align: center

==============================
Sheriff Azure DevOps Extension
==============================

-----
About
-----

This is a Github Action that provides an interface to `plan` command for
`Sheriff <https://github.com/gofrontier-com/sheriff>`_, a command line tool to
manage Azure role-based access control (Azure RBAC) and Microsoft Entra
Privileged Identity Management (Microsoft Entra PIM) using desired state configuration.

-----
Usage
-----

~~~~~~~~~~~~~~~~~~~~~~
Sheriff Plan action
~~~~~~~~~~~~~~~~~~~~~~

This task runs the plan action of Sheriff CLI on the agent. The ``configDir`` will point to
the location of the configuration files. Mode describes whether Sheriff will perform the actions
on `group` or `resources`. The `subscriptionId` is the Azure subscription ID.

.. code:: yaml

  - name: Log in with Azure
      uses: azure/login@v1
      with:
        creds: '${{ secrets.AZURE_CREDENTIALS }}'

  - name: Sheriff Plan
    uses: gofrontier-com/sheriff-plan-action@initial-work
    with:
      configDir: config/resources
      mode: azurerm
      subscriptionId: '${{ secrets.SUBSCRIPTION_ID }}'

------------
Contributing
------------

We welcome contributions to this repository. Please see `CONTRIBUTING.md <https://github.com/gofrontier-com/sheriff-azure-devops-extension/tree/main/CONTRIBUTING.md>`_ for more information.