
# rails2-upgrade

##### Preparing your app for rails 3 upgrade


######  This plugin is will bind the script to **git status/ git st** command, so whenever you make changes to the source code git st will also display the depicated content and possible alternative solutions to make changes on the files that are changed.


The plugin uses the **rals-upgrade.yml** file to record all the depricated patterns in rails2.

copy the files to your source code and add it to your path.

rails-upgrade.yml :


	depricated : 
		this section is a list of patterns which are depricated for views/models/controllers.

	alternatives: 
		in thhis section you can record the possible solutions(links/description) in the format "pattern - solution" which will be displayed with the warning. pattern here is the same as pattern recorded in depricated section.


usage :

first time usage : ruby git-rails-upgrade
				   This will create an git alias for "git st"

later usage : **git st**

it should output something similar

```
On branch xxx
Your branch is ahead of 'origin/8.0' by 1 commit.
  (use "git push" to publish your local commits)
Changes not staged for commit:

	modified:   xxx

no changes added to commit (use "git add" and/or "git commit -a")

Following files has a depricated rails 2 code..

app/controllers/xxx_controller.rb =>
	 link_to_remote
	 possible alternative :
		 link_to_remote - http://stackoverflow.com/questions/5511787/rails-2-to-rails-3-using-link-to-instead-of-link-to-remote-including-remote-a

 Depricated RHTML ext found : app/views/pages/xxx.rhtml => app/views/pages/xxx.erb
 
 ```



