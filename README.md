TeammatesTesting
================
<small>Used for building and testing the branches</small>

<h5>To get a branch forked from Teammates to be tested automatically on our testing station, plesae follow these steps:</h5>
<br>
<br>
<ol type='1'>
<li>Clone this repository to your local system.</li>
<li>Switch to the master branch (<code>git checkout master</code>)</li>
<li>Tag the latest commit with in the following format:
	<ol type='a'>
		<li>Tag Name: {remote}---{branch}. Eg: origin---master</li>
		<li>Tag Message: <i>Watch this space for more flexibility running tests</i></li>
		<li>Push just the tag to the remote (<code> git push origin {tag_name}</code>)</li>
	</ol><br>
	Or simply: <br><code>git tag -a {remote}---{branch} -m "{tag-message}"</code><br><code>git push origin {remote}---{branch}</code>
</li>
<li>If you would like run a branch again, simply push the tag to the remote again (<code>git push origin {remote}---{branch}</code>)</li>
</ol>
<br><br>
Please use the issue tracker to let us know of any bugs/problems that you may face.<br><br>
Enjoy the TeammatesTesting system!
