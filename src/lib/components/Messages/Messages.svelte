<script>
  let statuses = {
    Completed: 'text-green-400 bg-green-400/10',
    Error: 'text-rose-400 bg-rose-400/10'
  };
  let items = [
    {
      offset: 0,
      status: 'Error',
      transaction: { name: 'x-stream-transaction-id', value: 'transaction_0' },
      timestamp: '2023-10-22T17:18:56.738Z',
      data: 'test'
    }
  ];
</script>

<div
  class="dark:highlight-white/5 relative h-[calc(100%-250px)] overflow-hidden rounded-lg border-2 border-slate-50 dark:border-slate-400"
>
  <div class="flex h-full flex-col">
    <div class="flex items-center justify-between p-4">
      <p
        class="text-dashboards-xs text-neutral-850 mr-2 truncate font-medium leading-normal transition-all group-hover:mr-2 dark:text-white"
        title="Number of recent departures"
      >
        Messages
      </p>
    </div>
    <div class="relative flex h-[calc(100%-58px)] grow flex-col p-4">
      <table class="mt-2 flex h-full w-full flex-col whitespace-nowrap text-left dark:bg-slate-900">
        <thead
          class="w-[calc(100%-0.9em)] shrink-0 grow-0 basis-auto border-b border-white/10 text-sm leading-6 text-white"
        >
          <tr class="table w-full table-fixed">
            <th scope="col" class="w-1/12 py-2 font-semibold sm:table-cell">Offset</th>
            <th scope="col" class="w-3/12 py-2 text-right font-semibold sm:pr-8 sm:text-left"
              >Transaction</th
            >
            <th scope="col" class="w-4/12 py-2 text-right font-semibold sm:pr-8 sm:text-left"
              >Data</th
            >
            <th scope="col" class="w-1/12 py-2 font-semibold sm:table-cell">Status</th>
            <th scope="col" class="w-2/12 py-2 font-semibold md:table-cell">Timestamp</th>
            <th scope="col" class="w-1/12">Actions</th>
          </tr>
        </thead>
        <tbody
          class="grow-1 shrink-1 scrollbar-styled block basis-auto divide-y divide-white/5 overflow-y-scroll"
        >
          {#each Array(50) as _, i}
            <tr class="table w-full table-fixed">
              <td class="w-1/12 py-4 pr-4 sm:pr-8">
                <div class="flex gap-x-3">
                  <div
                    class="rounded-md bg-gray-700/40 px-2 py-1 text-xs font-medium text-gray-400 ring-1 ring-inset ring-white/10"
                  >
                    {items[0].offset}
                  </div>
                </div>
              </td>
              <td class="w-3/12 py-4 pr-8 text-sm leading-6 text-gray-400"
                >{items[0].transaction.value}</td
              >
              <td class="w-4/12 py-4 pr-8 text-sm leading-6 text-gray-400">{items[0].data}</td>
              <td class="w-1/12 py-4 pr-4 text-sm leading-6 sm:pr-8">
                <div class="flex items-center justify-end gap-x-2 sm:justify-start">
                  <div class={statuses[items[0].status] + ' flex-none rounded-full p-1'}>
                    <div class="h-2 w-2 rounded-full bg-current" />
                  </div>
                  <div class="hidden text-white sm:block">{items[0].status}</div>
                </div>
              </td>
              <td class="w-2/12 py-4 pr-8 text-sm leading-6 text-gray-400">{items[0].timestamp}</td>
              <td class="w-1/12 py-4 pr-8 text-sm leading-6 text-gray-400"
                ><a
                  href="#"
                  class="rounded bg-rose-400 px-2 py-1 text-sm font-semibold text-white shadow-sm hover:bg-rose-500 focus-visible:outline focus-visible:outline-2 focus-visible:outline-offset-2 focus-visible:outline-rose-500"
                  >Replay<span class="sr-only">Replay</span></a
                ></td
              >
            </tr>
          {/each}
        </tbody>
      </table>
    </div>
  </div>
</div>