More info @ https://github.com/wrr/wwwhisper

Simple nginx reverse proxy that hides container services that is linked on port 80 behind protected areas..

# Run #

Example, if you start this container with:

    docker run -d -e "SITE_URL=http://admin.your.domain" -e "ADMIN_MAIL=your@mail.com" -p 80:80 --link gitlab_1:git xeor/wwwhisper

It will create a web resource that shares port 80 on the container named gitlab_1 under admin.your.domain/git protected by wwwhisper and with your@mail.com as the admin account.
If you link several containers, they will all be setup as reverse proxy resources as long as they export port 80.


# admin #
Is available via /wwwhisper/admin/