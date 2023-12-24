
- **Make mock data to test :** 
	- [How to make fake data in Splunk using SPL · GitHub](https://gist.github.com/bshuler/5d0d75ac43ed8f57809fed6b60c4bfca)
	- Paste the data in the search bar and execute
	- ![[Pasted image 20231221115532.png]]
- **Add comments to Splunk**
	- [Using comments in SPL2 - Splunk Documentation](https://docs.splunk.com/Documentation/SCS/current/Search/Comments)

- **Run scheduled alert** 
	- [Manually Trigger Scheduled Saved Search - Splunk Community](https://community.splunk.com/t5/Reporting/Manually-Trigger-Scheduled-Saved-Search/m-p/97336)
		- To get that first artifact, I always just schedule the search for 1 minute in the future via cron (example: it is now 3:23pm, set it for `24 15 * * *`). Then I let it run, generate the saved artifact to check out in my dashboard, then when it's right I set it to the final schedule it needs to have.
- **Removing fields** 
	- [Solved: Removing fields vs. search performance - Splunk Community](https://community.splunk.com/t5/Splunk-Search/Removing-fields-vs-search-performance/m-p/564724#:~:text=By%20default%2C%20the%20_raw%20field,that%20data%20and%20increase%20performance%2C.)
