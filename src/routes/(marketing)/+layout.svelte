<script>
import { Nav, Footer } from '$lib/components'
import { page } from '$app/stores'

let hellobar = $page.data.store?.hellobar || {}
</script>

<div class="h-rem w-full flex-1">
	<Nav me="{$page.data.me}" cart="{$page.data.cart}" />

	<div
		class="w-full flex-1
			{hellobar?.active?.val && $page.data.store?.isHyperlocal
			? 'mt-[114px] sm:mt-[206px] lg:mt-[182px]'
			: ''}
			{hellobar?.active?.val ? 'mt-[88px] sm:mt-28 lg:mt-[88px]' : ''}
			{$page.data.store?.isHyperlocal ? 'mt-20 sm:mt-[104px] lg:mt-20' : ''}
			{!hellobar?.active?.val && !$page.data.store?.isHyperlocal ? 'mt-14 sm:mt-20 lg:mt-14' : ''}
			">
		<slot />
	</div>
</div>

<div class="hidden lg:block">
	<Footer me="{$page.data.me}" cart="{$page.data.cart}" />
</div>
