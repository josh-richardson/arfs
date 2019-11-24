<script>
    export let name;

    const Arweave = require('arweave/node');
    const arweave = Arweave.init({
        host: document.location.host.indexOf('localhost') !== -1 ? 'arweave.net' : document.location.host,
        port: 443,
        protocol: 'https',
    });

    arweave.network.getInfo().then(console.log);

    const ipfsClient = require('ipfs-http-client')

    const ipfs = ipfsClient({
        host: "51.159.59.187",
        port: "5001",
        protocol: "http"
    });

    ipfs.get('QmdMsmBqFQyiPQeS8vqPEjC3gZ4xo4Ev1wXzrcUiJYbPNq').then(r => {
        console.log(r.content.toString('utf8'))
    });
</script>

<style>
    h1 {
        color: purple;
    }
</style>

<h1>Hello {name}!</h1>

