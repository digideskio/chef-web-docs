.. The contents of this file may be included in multiple topics (using the includes directive).
.. The contents of this file should be modified in a way that preserves its ability to appear in multiple topics.


|chef| has the following major components:

.. list-table::
   :widths: 100 400
   :header-rows: 1

   * - Component
     - Description
   * - .. image:: ../../images/icon_workstation.svg
          :width: 100px
          :align: center

       .. image:: ../../images/icon_cookbook.svg
          :width: 100px
          :align: center

       .. image:: ../../images/icon_ruby.svg
          :width: 100px
          :align: center

     - One (or more) workstations are configured to allow users to author, test, and maintain cookbooks. Cookbooks are uploaded to the |chef server| from the workstation. Some cookbooks are custom to the organization and others are based on community cookbooks available from the |supermarket|.

       |ruby| is the programming language that is the authoring syntax for cookbooks. Most recipes are simple patterns (blocks that define properties and values that map to specific configuration items like packages, files, services, templates, and users). The full power of |ruby| is available for when you need a programming language.

       Often, a workstation is configured to use the |chef dk| as the development toolkit. The |chef dk| is a package from |chef| that provides an optional (but recommended) set of tooling, including |chef| itself, the |chef ctl| command line tool, |kitchen|, |chef spec|, |berkshelf|, and more.

   * - .. image:: ../../images/icon_node.svg
          :width: 100px
          :align: center

       .. image:: ../../images/icon_chef_client.svg
          :width: 100px
          :align: center

     - .. include:: ../../includes_node/includes_node.rst

       A |chef client| is installed on every node that is under management by |chef|. The |chef client| performs all of the configuration tasks that are specified by the run-list and will pull down any required configuration data from the |chef server| as it is needed during the |chef client| run.
   * - .. image:: ../../images/icon_chef_server.svg
          :width: 100px
          :align: center

     - The |chef server| acts as a hub of information. Cookbooks and policy settings are uploaded to the |chef server| by users from workstations. (Policy settings may also be maintained from the |chef server| itself, via the |chef manage| web user interface.)

       The |chef client| accesses the |chef server| from the node on which it's installed to get configuration data, perform searches of historical |chef client| run data, and then pull down the necessary configuration data. After the |chef client| run is finished, the |chef client| uploads updated run data to the |chef server| as the updated node object.

       |chef manage| is the user interface for the |chef server|. It is used to manage data bags, attributes, run-lists, roles, environments, and cookbooks, and also to configure role-based access for users and groups.
   * - .. image:: ../../images/icon_chef_supermarket.svg
          :width: 100px
          :align: center


     - |supermarket| is the location in which community cookbooks are authored and maintained. Cookbooks that are part of the |supermarket| may be used by any |chef| user. How community cookbooks are used varies from organization to organization.
