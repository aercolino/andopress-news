# AndoPress News

This WordPress plugin will connect to my remote service (at andowebsit.es) and receive the latest news (and executable 
modules) about any other AndoPress plugin. 

Example. Before updating from Enzymes 2 to Enzymes 3 users needed to backup their templates. I had no way to allow this, 
not automatically nor manually, because of the lack of an independent communication channel between the author of a 
plugin and its users. In fact, the only active channel is updates: Users will get automatically notified of a new 
version and when they automatically update, their templates will be automatically deleted.

AndoPress News will hook into the update plugins cron job (using set_site_transient_update_plugins, which is 
fired by WordPress every 12 hours), and post the date of its local latest news to my remote service.

If the date of the remote latest news is greater than that of the local, the service responds with all the news from 
that to the latest, otherwise it responds with a null.

When AndoNews receives non null news, it hooks into the dashboard and shows the latest news to each admin user.
