# Shared Pools and Definitions

Shared effect target pools, New World hotel needs and other definitions to use as sub-mod.

The modloader will always load the latest version.
You do not need to update your sub-mod if you don't need the new features yourself.

## Do not modify contents of this mod

Making changes may break mods and cause compatibility issues.

Go to [github.com/anno-mods/shared-resources](https://github.com/anno-mods/shared-resources) and create an issue to make change suggestions.

## How to Use

Copy the `[Shared] Pools and Definitions` into your mod and add `shared-pools-and-definitions` to your `LoadAfterIds`.

### Pools

Generic approach:

```xml
<!-- add to pools having sand mine -->
<ModOp Type="add"
  Path="//ItemEffectTargetPool/EffectTargetGUIDs[Item/GUID='1010560']">
  <Item>
    <GUID>1500010708</GUID> <!-- NW Sand Pit -->
  </Item>
</ModOp>
```

Fast approach:
```xml
<!-- add to sand pool -->
<ModOp Type="add" GUID="1500010714"
  Path="/Values/ItemEffectTargetPool/EffectTargetGUIDs">
  <Item>
    <GUID>1500010708</GUID> <!-- NW Sand Pit -->
  </Item>
</ModOp>
```

### Insert into Progression Menus by Unlock

Inserting into construction menus at the right spot while ensuring no other mods break your entry is quite cumbersome.

`shared-pools-and-definitions` allows you to insert using population progress instead of GUIDs.

Snippet:

```xml
<ModOp Type="addNextSibling" GUID="25000190"
  Path="/Values/ConstructionCategory/BuildingList/Item[Worker&lt;=400][last()]">
  <Item>
    <Building>1500010111</Building>
    <Worker>400</Worker>
  </Item>
</ModOp>
```

Result:

![](./../doc/menu-result.png)

#### Menu Unlock Guide

- Always add your own unlock condition
- If there's no unlock in this region, use the consumer unlock instead. E.g. Rum has no unlock in the OW, but consumption starts at 500 Artisans
- For production chains: use the tab of the highest workforce in the chain
- For construction categories: use the tab of the lowest workforce/consumer in the chain
- Include previous population if you add an entry to a lower tier, e.g. add `Farmer` if you want to add an `Worker` unlocked chain into the Farmers tab.

Currently available populations are:

Menu | GUID | Valid Tags
---|---|---
Farmers | 25000189 | `Farmer`, `Worker`, `Artisan`, `Engineer`, `Investor`
Workers | 25000190 | `Worker`, `Artisan`, `Engineer`, `Investor`
Artisans | 25000191 | `Artisan`, `Engineer`, `Investor`
Tourists | 132779 | `Tourist`, `Artisan`, `Investor`
Engineers | 25000192 | `Engineer`, `Investor`
Investors | 500447 | `Investor`
Jornaleros | 25000193 | `Jornalero`, `Obrero`, `Artista`
Obreros | 25000194 | `Obrero`, `Artista`
OW Consumables | 500945 | `Farmer`, `Worker`, `Artisan`, `Tourist`, `Engineer`, `Investor`, `Scholar`

Feel free to contribute other populations as well.

### Hotel Needs

```xml
<!-- copy needs from vanilla/NW Tourism hotel -->
<ModOp Type="add" GUID="601379" Path="/Values/PopulationLevel7/PopulationInputs/Item/RequiredBuildings[Item/Region='Moderate']">
  <Item>
    <RequiredBuilding>1500010500</RequiredBuilding>
    <Region>Moderate</Region>
  </Item>
</ModOp>
<ModOp Type="add" GUID="601379" Path="/Values/PopulationLevel7/PopulationInputs/Item/RequiredBuildings[Item/Region='Colony01']">
  <Item>
    <RequiredBuilding>1500010529</RequiredBuilding>
    <Region>Colony01</Region>
  </Item>
</ModOp>
```

When adding a need, make sure to flag the region.

```xml
<ModOp Type="addNextSibling" GUID="601379" Path="/Values/PopulationLevel7/PopulationInputs/Item[Product='1010213']">
  <Item>
    <Product>1500300060</Product>
    <Amount>0.008333333</Amount>
    <SupplyWeight>55</SupplyWeight>
    <MoneyValue>55</MoneyValue>
    <FullWeightPopulationCount>30</FullWeightPopulationCount>
    <NoWeightPopulationCount>29</NoWeightPopulationCount>
    <RequiredBuildings>
      <Item>
        <RequiredBuilding>601445</RequiredBuilding>
        <Region>Moderate</Region>
      </Item>
    </RequiredBuildings>
  </Item>
</ModOp>
```

Do the following if you want to remove a need, e.g. bread from OW hotels.

```xml
<ModOp Type="remove" GUID="601379"
    Path="/Values/PopulationLevel7/PopulationInputs/Item[Product='1010213']/RequiredBuildings/Item[Region='Moderate']" />
```

Never replace a need, always remove and add.

### Construction Menu Descriptions

The mod enableds you to change the words "Production Chain" in the construction chain InfoTip.

![](../doc/construction-infotip.jpg)

**Production Chains:**

```xml
<Asset>
  <Template>ProductionChain</Template>
  <Values>
    <Standard>
      <InfoDescription><!-- Text GUID --></InfoDescription>
    ...
```

Changing the description of categories and buildings is possible already possible in vanilla.

**Production Categories:**

```xml
<Asset>
  <Template>ConstructionCategory</Template>
  <Values>
    <ConstructionCategory>
      <CategoryDescription><!-- Text GUID --></CategoryDescription>
    ...
```

**Buildings:**

```xml
  <Asset>
    <Template>FactoryBuilding7</Template>
    <Values>
      <Building>
        <BuildingCategoryName><!-- Text GUID --></BuildingCategoryName>
        ...
```

## Changes
- 8.3: Adjust/add pools (Kurila)
- 8.2: Updated Korean translations (thanks to modpark817)
- 8.2: Added Timber production pool
- 8.1: Add NW Docklands need to tourists only when `NewWorldDocklands` is active
- 8: Replace NW tourist need of fur coats with ponchos
- 7: Added pools for motor assembly plant and subway station
- 7: Renamed most pool names from plural / 'all' to singular
- 6: Added pools for oil power plants, and various other productions
- 6: Renamed `assets-pools.xml` to `assets-pools.include.xml`
