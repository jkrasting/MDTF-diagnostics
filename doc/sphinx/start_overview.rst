Overview
========

Welcome! In this section we'll describe what the MDTF diagnostics framework is, how it works, and how you can contribute your own diagnostic scripts.

Purpose
-------

The scientific motivation and content behind the framework was described in E. D. Maloney et al. (2019): Process-Oriented Evaluation of Climate and Weather Forecasting Models. *BAMS*, **100** (9), 1665–1686, `doi:10.1175/BAMS-D-18-0042.1 <https://doi.org/10.1175/BAMS-D-18-0042.1>`__.

Also see the section of this site devoted to documentation of :doc:`individual diagnostics <pod_summary>`.

Framework operation
-------------------

The design goal of the MDTF framework is to provide a portable and adaptable means to run process-oriented diagnostic scripts, abbreviated as PODs below. By “portability,” we mean the ideal of “run once, run anywhere”: the purpose of the framework is to automate retrieval of model data from different local or remote sources, and transform that data into a layout (field names, variable units, etc.) your script expects. This will empower your analysis to be run by a wider range of researchers on a wider range of models.

.. figure:: ../img/dev_flowchart.jpg
   :align: center
   :width: 100 %

The MDTF Diagnostic Framework consists of multiple Process-Oriented Diagnostic (POD) modules, each of which is developed by an individual research group. For clarity, the framework is the structure provided by the Model Diagnostics Task Force, and the PODs (or modules) are developed by individual groups (or developers). PODs are developed and run independently of each other. Each POD takes as input (1) requested variables from the model run, along with (2) any required observational or supporting data, performs an analysis, and produces (3) a set of figures which are presented to the user in a series of .html files. (We do not include or require a mechanism for publishing these webpages on the internet; html is merely used as a convenient way to present a multimedia report to the user.)

Getting started for users
-------------------------

The rest of the documentation in this section describes next steps for end users of the framework:

- We provide instructions on how to :doc:`download and install <start_install>` the framework and run it on some sample data.
- We describe the most common :doc:`configuration options <start_config>` for running the framework on your own model data.
- See also the list of :doc:`command-line options <ref_cli>`.
- Known :doc:`troubleshooting issues <start_troubleshoot>`; also see the GitHub `issue tracker <https://github.com/NOAA-GFDL/MDTF-diagnostics/issues>`__.

Getting started for developers
------------------------------

As summarized in the figure above, the changes needed to convert an existing analysis script for use in the framework are:

- Provide a settings file which tells the framework what it needs to do: what languages and libraries your code need to run, and what model data your code takes as input.
- Adapt your code to load data files from locations set in unix shell environment variables (we use this as a language-independent way for the framework to communicate information to the POD).
- Provide a template web page which links to, and briefly describes, the plots generated by the script.

Each of these are described in more detail in the developer-specific sections:

- We provide instructions on :doc:`working with git <dev_git_intro>` for people who haven't used it before.
- :doc:`Instructions <dev_instruct>` and framework policies to keep in mind when developing your POD.
- Description of the :doc:`settings file <dev_settings_quick>` needed by the framework to process your POD's requirements.
- A more detailed :doc:`walkthrough <dev_walkthrough>` that elaborates on the flowchart above and describes the steps taken by the framework in order to run your POD.
- A :doc:`checklist <dev_checklist>` of items needed for submitting your POD for inclusion in the framework.
- A collection of :doc:`links <dev_general>` to relevant tutorials and resources.