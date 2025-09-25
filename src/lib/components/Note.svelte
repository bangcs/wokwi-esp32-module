<script>
  export let type = 'info'; // 'info' | 'warning' | 'danger' | 'success'

  // Mapping warna
  const styles = {
    info: 'bg-blue-50 border-blue-500 text-blue-800',
    warning: 'bg-yellow-50 border-yellow-500 text-yellow-800',
    danger: 'bg-red-50 border-red-500 text-red-800',
    success: 'bg-green-50 border-green-500 text-green-800'
  };

  const icons = {
    info: 'ℹ️',
    warning: '⚠️',
    danger: '🚨',
    success: '✅'
  };
</script>

<div class={`note my-6 p-4 rounded-lg border-l-4 bg-gray-50 shadow-sm ${styles[type]}`}>
  <div class="flex items-start">
    <span class="text-lg mr-3">{icons[type]}</span>
    <div class="flex-1"><slot /></div>
  </div>
</div>