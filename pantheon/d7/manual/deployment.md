## Deployment

1. Merge develop into master.
2. Push master to Pantheon.
3. `terminus dashboard PANTHEON_SITE.test`
4. Enter the tickets you are deploying into the deployment notes and click Deploy
5. Click the "Live" tab.
6. Repeat step 4.
7. run the following commands as needed:
  ```
  terminus drush PANTHEON_SITE.live -- updb -y
  terminus drush PANTHEON_SITE.live -- cc all -y
  terminus drush PANTHEON_SITE.live -- fra -y
  terminus drush PANTHEON_SITE.live -- cc all -y
  ```
