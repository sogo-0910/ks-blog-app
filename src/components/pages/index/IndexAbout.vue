<template>
  <BaseContent padding-y="top">
    <BaseHeadingLevel1 id="anchor-01" markup="h2">About</BaseHeadingLevel1>
    <MediaLayout type-sp="columnReverse" type-pc="rowReverse" filter="blur">
      <template #content>
        <BaseText>
          <p>
            サイトをご覧いただきありがとうございます。<br>都内でフロントエンドエンジニアをしているK・Sです。
          </p>
          <p>大規模なサイトのコンポーネント作成・アクセシビリティ対応・マネジメント能力を強みに活動しています...</p>
        </BaseText>
        <BaseButton :to="PATHS.ABOUT.path">Show more</BaseButton>
      </template>
      <template #media>
        <BaseMedia
          src="/about/img/about-01.webp"
          width="300"
          height="300"
          loading="lazy"
          type="circle"
        />
      </template>
    </MediaLayout>
  </BaseContent>
</template>

<script setup lang="ts">
  import BaseContent from '~/components/atoms/BaseContent.vue'
  import BaseHeadingLevel1 from '~/components/atoms/BaseHeadingLevel1.vue'
  import BaseText from '~/components/atoms/BaseText.vue'
  import BaseMedia from '~/components/atoms/BaseMedia.vue'
  import BaseButton from '~/components/atoms/BaseButton.vue'
  import MediaLayout from '~/components/molecules/MediaLayout.vue'
</script>
