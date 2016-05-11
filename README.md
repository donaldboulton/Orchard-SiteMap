# Orchard-SiteMap
SiteMap module for Orchard CMS
Has been rebuilt for Orchard 1.10.1x

need to add the below to your Orchard.Web root web.config file so Orchard Caching does not destroy it.

<httpHandlers>
        <clear />
        <add verb="*" path="sitemap.xml" type="System.Web.StaticFileHandler" />
</httpHandlers>
And then
<add extension=".xml" policy="DisableCache" kernelCachePolicy="DisableCache>
Like below. Orchard Caching kills .rss and .xml

 </staticContent>
    <caching>
        <profiles>
            <add extension=".xml" policy="DontCache" kernelCachePolicy="DontCache" />
            <add extension=".rss" policy="DontCache" kernelCachePolicy="DontCache" />
        </profiles>
    </caching>
  </system.webServer>
