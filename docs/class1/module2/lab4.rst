Lab 2.4: Security workflows
---------------------------
Connect as **larry** with password of **larry**

Check the Firewall policy.

Go to Monitoring > REPORTS > Security > Network Security > Rule statistics and select
*vs_site18.example.com_https* SEA-vBIGIP01.termmarc.com

.. image:: ../pictures/module2/img_module2_lab4_1.png
  :align: center
  :scale: 50%

|

Check the Web Application Security for ``f5-asm-policy1`` ASM Policy.

Go to Configuration > SECURITY > Web Application Security > Policies

Click on Suggestions, then **Accept** the Learning.

.. image:: ../pictures/module2/img_module2_lab4_3.png
  :align: center
  :scale: 50%

|

Still logged in as Larry, go to Deployment > EVALUATE & DEPLOY > Web Application Security

Under Deployments, click on **Create**. Name your Deployment, select SEA-vBIGIP01.termmarc.com, choose method **Deploy immediately**, then click on **Create**.

.. image:: ../pictures/module2/img_module2_lab4_3b.png
  :align: center
  :scale: 50%

|

Go back to Configuration > SECURITY > Web Application Security > Policies

Update the Enforcement Mode to ``Blocking``.

.. image:: ../pictures/module2/img_module2_lab4_4.png
  :align: center
  :scale: 50%

|

Connect as **paula** with password of **paula**

Select ``site18.example.com``

Enforce the policy APPLICATION SERVICES > Security > CONFIGURATION tab > click on ``Start Blocking``

.. image:: ../pictures/module2/img_module2_lab4_5.png
  :align: center
  :scale: 50%

|

.. image:: ../pictures/module2/img_module2_lab4_6.png
  :align: center
  :scale: 50%

|

.. note:: The Enforcement Mode is controlled by the Application owner, the Host Name of the application (FQDN) will be configured in the ASM Policy to enforce it (or not)

.. image:: ../pictures/module2/img_module2_lab4_6a.png
  :align: center
  :scale: 50%

|

Let's generate some bad traffic, connect on the *Ubuntu Lamp Server* server and launch the following script:

``# /home/f5/scripts/generate_bad_traffic.sh``

In the Application Dashboard, navigate to the Security Statistics and notice the Malicious Transactions.

Connect as **larry** with password of **larry**

Check ASM type of attacks

Monitoring > EVENTS > Web Application Security > Event Logs > Events

.. image:: ../pictures/module2/img_module2_lab4_7.png
  :align: center
  :scale: 50%
