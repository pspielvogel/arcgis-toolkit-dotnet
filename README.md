arcgis-toolkit-dotnet
=====================

This project contains the set of controls for use with the Esri ArcGIS Runtime SDK for .NET.
Included are a number of controls you can use to enhance your applications. 


##What is in it?

ArcGIS Toolkit for .NET includes:

* `Legend` -  Displays a legend for a set of layers in your map.
* `Attribution` : Displays copyright/attribution information for layers in your map.
* `ScaleLine` : Displays current scale reference.
* `SignInDialog` (Desktop only) : SignIn dialog that challenges the user when accessign ArcGIS secured resources..

## How Do I Use It?
* Get the Github Repo by either cloning it or downloading the zip package from the master branch.
* Add the Esri.ArcGISRuntime.Toolkit project to your existing solution.
* Right-click the project where you want to use the toolkit, select 'Add reference', and pick the toolkit project under the solutions tab.
* Next register the xmlns namespace in the `Page` or `UserControl` where you want to use the control:

```xml
  xmlns:esriTK="using:Esri.ArcGISRuntime.Toolkit.Controls" 
```

<i>Note: Some of the following examples assumes an ArcGIS map control named 'MyMap' is present.</i>

####Legend
Set the `Layers` property to the collection of layers you want to show legend for.
If you only want to display layers that are visible at the current scale range, also set the `Scale` property. Set this to 'NaN' (or don't set it) to avoid filtering by layer scale visibility.
Both of these properties are available for binding directly from the map. Example:
```xml
  <esriTK:Legend Layers="{Binding Layers, ElementName=MyMap}" 
    Scale="{Binding Scale, ElementName=MyMap}" />
```
Other useful properties:
* `ShowOnlyVisibleLayers` - Don't show legend for layers not currently visible
* `ReverseLayersOrder` - Reverses the layer order to easily order layers so that layers that are on top in the map is showing first in the legend. If you want more control over the order, use a converter or bind the collection via your view model to create a more custom collection.

####Attribution
Simply set the `Layers` property to those layers that you want to display attribution for. Note that the terms of use for many services requires you to display some form of attribution, and this control will make that easy for you.
```xml
  <esriTK:Attribution Layers="{Binding Layers, ElementName=MyMap}" />
```

####ScaleLine
```xml
   <esriTK:ScaleLine Scale="{Binding Scale, ElementName=MyMap}" />
```

####SignInDialog (Desktop only)
The simplest way to use it is by setting the IdentityManager ChallengeMethod to the static DoSignIn:
```code
   IdentityManager.Current.ChallengeMethod = SignInDialog.DoSignIn;
```

## Resources

* [ArcGIS Runtime SDK for Windows Store apps](http://developers.arcgis.com/en/windows-store/)

## Issues

Find a bug or want to request a new feature?  Please let us know by submitting an issue.

## Contributing

Anyone and everyone is welcome to contribute. 

## Licensing
Copyright 2013 Esri

This source is subject to the Microsoft Public License (Ms-PL).
You may obtain a copy of the License at

   http://opensource.org/licenses/ms-pl

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.

A copy of the license is available in the repository's [license]( https://raw.github.com/Esri/arcgis-toolkit-dotnet/master/license) file.

[](Esri Tags: ArcGIS Runtime SDK .NET WinRT WinStore WPF WinPhone C# C-Sharp DotNet XAML)
[](Esri Language: DotNet)


