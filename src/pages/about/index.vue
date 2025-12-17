<template>
  <BaseContent>
    <BaseHeadingLevel1 sub-title="About">私について</BaseHeadingLevel1>
    <MediaLayout type-sp="columnReverse" type-pc="rowReverse" filter="blur">
      <template #content>
        <BaseText>
          <p>
            サイトをご覧いただきありがとうございます。<br>都内でフロントエンドエンジニアをしているK・Sです。
          </p>
          <p>大規模なサイトのコンポーネント作成・アクセシビリティ対応・マネジメント能力を強みに活動しています。</p>
          <p>これからフロントエンドに関する内容を中心に発信していく予定です。<br>本ブログが、皆さまの参考や励みになれば幸いです。</p>
        </BaseText>
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

    <AboutSkill />
  </BaseContent>
</template>

<script setup lang="ts">
  import BaseContent from '~/components/atoms/BaseContent.vue'
  import BaseHeadingLevel1 from '~/components/atoms/BaseHeadingLevel1.vue'
  import BaseText from '~/components/atoms/BaseText.vue'
  import BaseMedia from '~/components/atoms/BaseMedia.vue'
  import MediaLayout from '~/components/molecules/MediaLayout.vue'
  import AboutSkill from '~/components/pages/about/AboutSkill.vue'

  const breadcrumbState = useBreadcrumbState()

  breadcrumbState.value = [
    { name: 'HOME', path: '/' },
    { name: 'About', path: '/about' },
  ]

  const breadcrumbJsonLd = useBreadcrumbJsonLd(breadcrumbState?.value)

  useHead({
    title: 'About | KS BLOG',
    meta: [
      {
        name: 'description',
        content: 'KS BLOGはブログサイトです。サイト管理者についてをご紹介。',
      },
      {
        property: 'og:title',
        content: 'About | KS BLOG',
      },
      {
        property: 'og:description',
        content: 'KS BLOGはブログサイトです。サイト管理者についてをご紹介。',
      },
    ],
    script: [
      {
        key: 'breadcrumb-jsonld',
        type: 'application/ld+json',
        innerHTML: breadcrumbJsonLd.value,
      },
    ],
  })
</script>
