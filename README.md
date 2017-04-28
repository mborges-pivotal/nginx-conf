# nginx-conf

This project tests the sub_filter directive. In order to support this directive we
had to rebuild the static_buildpack to include the http_sub_module.

See [binary-build](https://github.com/cloudfoundry/binary-builder) to learn how to build
cloudfoundry buildpack binaries. And [static_buildpack](https://github.com/cloudfoundry/staticfile-buildpack)
for information on how to rebuild the buildpack with the new binaries.

We customized the deployment to include the directive based on the [doc](https://docs.pivotal.io/pivotalcf/1-10/buildpacks/staticfile/index.html) of the static buildpack.

There are 2 options:
* You can add a new nginx.conf file Or
* add the location_include option in the Staticfile

The only caveat with the second option is that you'll have to also use the alternative root
to ensure the include is place in the proper folder. 
