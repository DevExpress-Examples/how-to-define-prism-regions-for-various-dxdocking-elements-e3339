# How to define Prism regions for various DXDocking elements


<p>This example demonstrates how to use DXDocking with PRISM.</p>


<h3>Description</h3>

<p>Starting with version 17.1, you can use built-in PRISM adapters from the DevExpress.Xpf.PrismAdapters.vXX.X assembly. Here is how they can be registered:</p>

```cs
protected override void ConfigureRegionAdapterMappings(RegionAdapterMappings regionAdapterMappings)
{
    base.ConfigureRegionAdapterMappings(regionAdapterMappings);
    var factory = Container.Resolve<IRegionBehaviorFactory>();
    regionAdapterMappings.RegisterMapping(typeof(LayoutPanel), AdapterFactory.Make<RegionAdapterBase<LayoutPanel>>(factory));
    regionAdapterMappings.RegisterMapping(typeof(LayoutGroup), AdapterFactory.Make<RegionAdapterBase<LayoutGroup>>(factory));
    regionAdapterMappings.RegisterMapping(typeof(TabbedGroup), AdapterFactory.Make<RegionAdapterBase<TabbedGroup>>(factory));
    regionAdapterMappings.RegisterMapping(typeof(DocumentGroup), AdapterFactory.Make<RegionAdapterBase<DocumentGroup>>(factory));
}
```

```vb
Protected Overrides Sub ConfigureRegionAdapterMappings(ByVal regionAdapterMappings As RegionAdapterMappings)
	MyBase.ConfigureRegionAdapterMappings(regionAdapterMappings)
	Dim factory = Container.Resolve(Of IRegionBehaviorFactory)()
	regionAdapterMappings.RegisterMapping(GetType(LayoutPanel), AdapterFactory.Make(Of RegionAdapterBase(Of LayoutPanel))(factory))
	regionAdapterMappings.RegisterMapping(GetType(LayoutGroup), AdapterFactory.Make(Of RegionAdapterBase(Of LayoutGroup))(factory))
	regionAdapterMappings.RegisterMapping(GetType(TabbedGroup), AdapterFactory.Make(Of RegionAdapterBase(Of TabbedGroup))(factory))
	regionAdapterMappings.RegisterMapping(GetType(DocumentGroup), AdapterFactory.Make(Of RegionAdapterBase(Of DocumentGroup))(factory))
End Sub
```


