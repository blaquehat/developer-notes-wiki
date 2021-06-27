# Drush Commands

// If you need to rebuild a site with previous configs, run the following to sync site uuid.
drush -y cset system.site uuid $(cat config/sync/system.site.yml | awk '/uuid/ { print $2 }')

// SO you do not get:
//  Entities exist of type <em class="placeholder">Shortcut link</em> and <em class="placeholder">Shortcut set</em> <em class="placeholder">Default</em>. These entities need to be deleted before importing.
// Run the following in Drupal 9 before you cim.
drush entity:delete shortcut_set