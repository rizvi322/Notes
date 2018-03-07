CUE FRONT
==========

### Docker with local repositories
- Update `.env` file for developer override with all the extensions:

```bash
for ext in ../*; do name=$(echo $ext | cut -d'-' -f 4 | tr 'a-z' 'A-Z'); [ "$name" != "" ] && echo "EXTENSION_${name}_PATH=${ext}" >> .env ; done;
```

- Update `docker-compose-developer-override.yml` file with all extension:

```bash
for ext in ../*; do name=$(echo $ext | cut -d'-' -f 4 | tr 'a-z' 'A-Z'); [ "$name" != "" ] && echo "- \${EXTENSION_${name}_PATH}:/srv/$(echo $ext | cut -d'/' -f 2)/:ro" ; done;
```
<!--stackedit_data:
eyJoaXN0b3J5IjpbNDU5MjA1NjAxXX0=
-->