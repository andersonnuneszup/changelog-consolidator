# changelog-consolidator
Project destined to automate the changelog creation.

## Objective
* In order to facilitate the process of documenting project changes, this solution creates a process in which each developer writes a file that documents their change and when generating code consolidation in a main branch, a "github action" is triggered. which consolidates all merged files into one main file that centralizes all changes

## Prerequisites
* It is necessary that the project where this code is hosted on github;
* It is necessary that some project administrator user on github create a secret with the name "PRIVATE_ACCESS_TOKEN" in the project that contains the value of a token of a user with permission to write in the repository;

## How to use
*   Modifications fall into 3 categories:
	* Additions
	* Corrections
	* Improvements
*   This division is done in order to facilitate categorization in the consolidated file. Each type of modification will fit into a specific folder.
* The code is configured to commit the changelogs when there is a commit on the "master" branch. It is only in this action that the consolidation takes place, but it is possible to easily modify this behavior if the developer wants to.
* To exemplify, in the case of a developer creating a new functionality. It should create a txt file with the change information.   As a suggestion, we have the text below where the activity code is inserted in the activity management system used, a brief description of the new functionality and the author of the modification: 
	*  User registration entered in the system #289404 - by @andersonnuneszup
* After merging the code in the predetermined branch, an action will be executed that will read all the txts inside the 3 folders allocated inside the "unreleased" folder and insert their text inside the central file called "CHANGELOG.md"