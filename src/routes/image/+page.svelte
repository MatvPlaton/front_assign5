<script lang="ts">
    const email: string = 'm.platonov@innopolis.university';

    const params: URLSearchParams = new URLSearchParams();
    params.append('email', email);

    async function get_id(): Promise<string> {
        let response: Response = await fetch('https://fwd.innopolis.university/api/hw2?' + params.toString());
        return await response.text();
    }

    interface Data {
        alt: string;
        img: string;
        safe_title: string;
        year: string;
        month: string;
        day: string;
    }

    let Title: string;

    let img: string;

    let alt: string;

    let Date1: string;

    function load(data: Data): void {

        Title = data['safe_title']

        img = data['img']
        alt = data['alt']

        let year: number = parseInt(data['year'], 10);
        let month: number = parseInt(data['month'], 10) - 1;
        let day: number = parseInt(data['day'], 10);

        Date1 = new Date(year, month, day).toLocaleDateString();
    }

    async function get_data(res: string): Promise<void> {
        let url: string = 'https://fwd.innopolis.university/api/comic?id=' + res;
        let response: Response = await fetch(url);

        let data: Data = await response.json();
        load(data);
    }

    async function init(): Promise<void> {
        let id: string = await get_id();
        await get_data(id);
    }

    init();
</script>

<div>
    <div id="title"> Title: {Title} </div>
    <img alt={alt} title="" src={img}>
    <div style="position: absolute; left: 500px; top:8px"> Date: {Date1}</div>
</div>