# apachesolr_rss

This Drupal module provides search results from Apache SOLR as an RSS feed.

For each custom search page, such as <code>/mysearch/keywords</code>, this module creates a menu hook that inserts
'rss' between the search page path and the keywords, i.e. <code>/mysearch/rss/keywords</code>.  The SOLR search 
uses the supplied keyword from the URL as well as whatever query parameters are passed to the page.

The feed URL is automatically added to the top of the page as a link tag to allow browsers to
auto-discover the feed.  In addition, you can use the <code>apachesolr_rss_feed_url()</code> function to 
get the URL to the feed for the current page in order to render your own RSS icon. 

The <code>node_feed()</code> function is used to render an RSS feed of all search results.  This uses the 
built-in RSS display mode for the resulting nodes in order to assemble each RSS item.
You can implement <code>hook_node_view()</code> in order to override the RSS item and modify
the description field or add additional XML tags.

In addition, you can implement <code>apachesolr_rss_channel_alter()</code> to modify properties of the 
channel tag itself.  For instance, you may wish to include in the feed's description a summary of the 
keywords, facets and filters that were applied.  Since this happens outside the scope of the apachesolr
module, we leave it to the user to determine how best to format and display these elements.


## License

Copyright New Signature 2010 - 2011

This program is free software: you can redistribute it and/or modify it under the terms of the 
GNU General Public License as published by the Free Software Foundation, either version 3 of the 
License, or (at your option) any later version.

This program is distributed in the hope that it will be useful, but WITHOUT ANY WARRANTY; 
without even the implied warranty of MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  
See the GNU General Public License for more details.

You should have received a copy of the GNU General Public License along with this program.  
If not, see <http://www.gnu.org/licenses/>.

You can contact New Signature by electronic mail at labs@newsignature.com 
or- by U.S. Postal Service at 1100 H St. NW, Suite 940, Washington, DC 20005.