<script lang="ts">
	import dayjs from 'dayjs';
	import relativeTime from 'dayjs/plugin/relativeTime';

	dayjs.extend(relativeTime);

	let time_until_kaguya_sama: string = '';
	let time_checker = () => {
		let t = (unit: 'millisecond' | 'second' | 'minute' | 'hour' | 'day') => {
			let time = dayjs('15 Feb 2023 19:30:00 EST').diff(dayjs(), unit);

			let value: string;
			if (unit == 'millisecond') {
				value = (time % 1000).toLocaleString(undefined, {
					useGrouping: false,
					minimumIntegerDigits: 3,
				});
			} else if (unit == 'second' || unit == 'minute') {
				value = (time % 60).toLocaleString(undefined, {
					useGrouping: false,
					minimumIntegerDigits: 2,
				});
			} else if (unit == 'hour') {
				value = (time % 24).toLocaleString(undefined, {
					useGrouping: false,
					minimumIntegerDigits: 2,
				});
			} else if (unit == 'day') {
				value = time.toString()
			} else {
				value = '' // unreachable
			}

			return value;
		};

		time_until_kaguya_sama = `${t('hour')}:${t('minute')}:${t('second')}.${t('millisecond')}`;

		let days_left = parseInt(t('day'))
		if (days_left > 1) {
			time_until_kaguya_sama += ` + ${days_left} days!`
		} else if (days_left == 1) {
			time_until_kaguya_sama += " + 1 day!!!!!!"
		} else {
			time_until_kaguya_sama += " (soon!!!!!!!!!!!)"
		}

		setTimeout(time_checker, 100);
	};

	setTimeout(time_checker, 100);
</script>

<div class="flex h-screen">
	<div class="my-auto mx-auto text-center space-y-10">
		<h1 class="font-extrabold text-4xl">Time until I go watch Kaguya sama movie</h1>
		<p class="">{time_until_kaguya_sama}</p>
	</div>
</div>
