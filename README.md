TeammatesTesting
================
<small>Used for building and testing branches forked from Teammates project</small>
<br>
<h5>To Request a Test-run on our remote testing station:</h5>
<br>
<ol type='1'>
<li>Clone this repository to your local system.</li>
<li>Switch to the master branch (<code>git checkout master</code>)</li>
<li>Tag the latest commit with in the following format:
	<ol type='a'>
		<li>Tag Name: {remote}---{branch}. Eg: origin---master</li>
		<li>Tag Message: Anything for now. (<i>Watch this space for more flexibility running tests</i>)</li>
		<li>Push just the tag to the remote (<code> git push origin {tag_name}</code>)</li>
	</ol><br>
	Or simply: <br><code>git tag -a {remote}---{branch} -m "{tag-message}"</code><br><code>git push origin {remote}---{branch}</code>
</li><br>
<li>If you would like run a branch again, simply push the tag to the remote again: <br><code>git push origin {remote}---{branch}</code></li>
</ol>
<br><br>
<h5>To get the results and make sense of it:</h5>
<br>
<ol type='1'>
	<li>Once the remote stating is done testing the requested branch, it will upload the test results to a new branch in
		this repository (TeammatesTesting) with a branchname {remote}-{branch} based on the parameters specified in the tag
		that was used for the request.</li>
	<li>The following files will be uploaded as part of the test output:
		<ol type='a'>
			<li>A folder named test-output containing the final testng results based on the 5th run of the failed tests</li>
			<li>A text file named git-output.txt will contain the output from the git commands used to access the branch that was requested</li>
			<li>A text file named build-output.txt will contain the output of the ANT builder that is used to compile and enhance the app</li>
			<li>A text file named server-output.txt will contain the entire output from the server that was started (inc. logging from the main app)</li>
			<li>A text file named testng-output.txt will contain the entire output from the testng process (inc. logging from the tests)</li>
		</ol>
	</li><br>
	<li>If there were any errors while trying to run the branch, one of the following happens:
		<ol type='a'>
			<li>Invalid format: If the request does not comply to the {remote}---{branch} format, it is simply ignored</li>
			<li>Branch does not exist: If the requested branch does not exist in the specified remote, the git-output.txt will contain
				the error information and no other files will be uploaded to the new branch created in this repo</li>
			<li>Build error: if the version of the app on the branch does not compile/enhance, the build-output.txt file will contain all the required
				information to debug the build issue. The testng-output.txt will contain one line indicating that test did not run because building failed</li>
			<li>Testng Test Failures: All the failed test cases with all related information (testname, reason, any exceptions in the server, any exceptions in the testng process) will be packaged in the various text files that are uploaded with a summary view available at: test-output/index.html </li>
		</ol>
	</li><
</ol>
<br><br>
Please use the issue tracker to let us know of any bugs/problems that you may face.<br><br>
Enjoy the TeammatesTesting system!
