<script lang="ts">
	import kaguya_timer from '../components/kaguya_timer';
	let time_until_kaguya_sama: string = '';
	let time_checker = () => {
		time_until_kaguya_sama = kaguya_timer();
		setTimeout(time_checker, 100);
	};

	setTimeout(time_checker, 100);
</script>

<div class="flex flex-col">
	<div class="flex h-screen">
		<div class="my-auto mx-auto text-center space-y-10">
			<h1 class="font-extrabold text-4xl">I watched Kaguya sama movie</h1>
			<p class="">it was good</p>
		</div>
	</div>

	<div class="flex px-10 py-10 flex-col">
		<h1 class="font-bold text-xl mx-auto">About me</h1>
		<div class="grid grid-cols-3 space-x-10">
			<div class="flex flex-col">
				<h1>Github</h1>
				<p>Since 2020!</p>
				<a href="https://wakatime.com/@d06087a9-1552-4763-b7f2-3957dcd1dd86"
					><img
						src="https://wakatime.com/badge/user/d06087a9-1552-4763-b7f2-3957dcd1dd86.svg"
						alt="wakatime badge"
					/></a
				>
			</div>
			<div>
				<h1>Youtube</h1>
				<a href="https://www.youtube.com/@zbrachi">Channel</a>
			</div>
			<div>
				<h1>Placeholder</h1>
			</div>
		</div>
	</div>
</div>
