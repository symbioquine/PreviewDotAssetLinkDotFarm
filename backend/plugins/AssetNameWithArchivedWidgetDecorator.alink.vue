<template>
  <span><slot></slot> {{ '\u{1F5C3}' }}</span>
</template>

<script>
export default {
  onLoad(handle) {
    handle.defineWidgetDecorator('net.symbioquine.farmos_asset_link.widget_decorator.v0.asset_name_with_archived', widgetDecorator => {
      widgetDecorator.targetWidgetName('asset-name');

      widgetDecorator.appliesIf(context => context.asset.attributes.status === 'archived');

      widgetDecorator.weight(50);

      widgetDecorator.component(handle.thisPlugin);
    });
  }
}
</script>
