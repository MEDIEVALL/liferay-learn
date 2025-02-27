# Patching Earlier DXP Versions

```{toctree}
:maxdepth: 3

patching-dxp-7-3-and-earlier/understanding-patch-types-for-dxp-7-3-and-earlier.md
patching-dxp-7-3-and-earlier/installing-patches-for-dxp-7-3-and-earlier.md
patching-dxp-7-3-and-earlier/advanced-patching-for-dxp-7-2.md
```

```{note}
Liferay DXP 7.3 SP3+ follows a rolling release model that uses Updates. Please see [Updating Liferay](./updating-liferay.md) if you are applying an Update. All Hotfixes are patches. If you're applying a Hotfix, continue reading.
```

As Liferay releases fixes, you'll want to keep your DXP instances up to date. Liferay aggregates fixes and makes them available to Enterprise Subscribers in ZIP files called _patches_.

## Patch Types

There are several different kinds of patches, and they serve different purposes.

* **Fix Packs:** Resolve the most recent issues.
* **Security Fix Packs:** Address the latest security issues immediately.

**For all DXP versions**

* **Hotfixes:** Requested by customers to fix business critical DXP issues fast.

**For versions before DXP 7.3 SP3**

* **Fix Packs:** Resolve the most recent issues.
* **Security Fix Packs:** Address the latest security issues immediately. Note, Liferay DXP 7.3 SP3+ uses Security Updates. Please see [Updating Liferay](./updating-liferay.md) for details.
* **Service Packs:** Incorporate larger fixes that require more testing. Service Pack releases also include full DXP Service Pack Tomcat bundles.

[Understanding Patch Types](./patching-dxp-7-3-and-earlier/understanding-patch-types-for-dxp-7-3-and-earlier.md) explains the patch options above.

## Installing Patches

Once you have a patch you need, apply it using the Patching Tool. [Installing Patches](./patching-dxp-7-3-and-earlier/installing-patches-for-dxp-7-3-and-earlier.md) provides the basic steps for patching DXP safely and comprehensively.

## Configuring the Patching Tool

The [`patching-tool.sh auto-discovery` command](./reference/configuring-the-patching-tool.md) configures the tool automatically for Tomcat bundles and common app server configurations. You can also configure the Patching Tool manually to handle DXP installation variations.

## Other Patching Topics

As you apply patches, you may need to submit patch information in support requests or uninstall patches you no longer need.

* [Getting Patch Information](./reference/getting-patch-information.md)
* [Uninstalling Patches](./reference/uninstalling-patches.md)

## Patching DXP 7.2 

The following topics provide best practices for managing patches in DXP 7.2:

* [Slimming Down Patched Installations](./patching-dxp-7-3-and-earlier/advanced-patching-for-dxp-7-2/slimming-down-patched-installations.md)
* [Using Slim Bundles](./patching-dxp-7-3-and-earlier/advanced-patching-for-dxp-7-2/using-slim-bundles.md)
* [Handling Collisions between Patches and Custom Plugins](./patching-dxp-7-3-and-earlier/advanced-patching-for-dxp-7-2/custom-code-and-patch-compatibility.md)

Now that you've digested the patching overview, learn about the [Patch Types](./patching-dxp-7-3-and-earlier/understanding-patch-types-for-dxp-7-3-and-earlier.md) available to you. Then you'll be ready to apply patches following [Installing Patches](./patching-dxp-7-3-and-earlier/installing-patches-for-dxp-7-3-and-earlier.md).
