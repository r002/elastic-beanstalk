# Set up SSL certificate for single-instance Elastic Beanstalk

Here are the files described in: \
https://medium.com/edataconsulting/how-to-get-a-ssl-certificate-running-in-aws-elastic-beanstalk-using-certbot-6daa9baa3997

Thank you so much to [Marcos Escandell](https://medium.com/@memmarcos) for writing everything up! 🙏🙏🙏

The article works! But the formatting (eg. indentations) got lost in the config snippets which are mandatory to make elastic beanstalk understand your configuration.

So I put a working version of everything here in this repo. Enjoy! Free SSL on EB for everyone! 😀

### Final Result:
![image](https://user-images.githubusercontent.com/45280066/114209882-22b81700-992d-11eb-8197-ab8279c4e8ab.png)

---

### One gotcha:

If you are uploading from Windows, you will get this cryptic error (`Stderr:/usr/bin/env: bash: No such file or directory`):

![image](https://user-images.githubusercontent.com/45280066/114210243-893d3500-992d-11eb-84b3-424787f158da.png)

[It's because Windows uses different "End of Line" (EOL) characters than unix does.](https://stackoverflow.com/questions/18172405/getting-error-usr-bin-env-sh-no-such-file-or-directory-when-running-command-p)

You can easily fix the problem in Notepad++ for the `\.platform\hooks\postdeploy\00_get_certificate.sh` file:

![image](https://user-images.githubusercontent.com/45280066/114211079-3152fe00-992e-11eb-8d6b-4618086a2623.png)

---

### Reference:

- https://docs.aws.amazon.com/elasticbeanstalk/latest/dg/https-singleinstance-go.html
