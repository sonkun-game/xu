<template>
    <div class="w-screen h-screen flex">
        <table class="table-auto m-auto shadow">
            <thead>
                <tr class="p-4">
                    <th class="p-4" v-for="(item, index) in table.head" :key="index">
                        {{ item.name }}
                    </th>
                </tr>
            </thead>
            <tbody>
                <tr class="p-4" v-for="(item,index) in table.body" :key="'tbody' + index">
                    <td class="p-4">{{ index + 1 }}</td>
                    <td class="p-4">{{ item.group }}</td>
                    <td class="p-4">{{ item.command }}</td>
                    <td class="p-4">
                        <div v-for="(subItem,subIndex) in item.option" :key="subItem + subIndex" class="border-b">
                            {{ subItem }}
                        </div>
                    </td>
                    <td class="p-4">
                        <div v-for="(subItem,subIndex) in item.option" :key="subItem + subIndex" class="border-b">
                            {{ item.command + " " + subItem }}
                        </div>
                    </td>
                    <td class="p-4">
                        Guide
                    </td>
                </tr>
            </tbody>
            <tfoot>

            </tfoot>
        </table>
    </div>
</template>

<script>

export default {
    name: "GitIntroducePage",
    data() {
        return {
            table: {
                head: [
                    {
                        name: "STT"
                    },
                    {
                        name: "Group"
                    },
                    {
                        name: "Command"
                    },
                    {
                        name: "Option"
                    },
                    {
                        name: "FullCommand"
                    },
                    {
                        name: "Guide"
                    }
                ],
                body: [
                    {
                        group: "branch",
                        command: "git branch",
                        option: [
                            "--no-color",
                            "--show-current",
                            "-v",
                            "--abbrev=<n>",
                            "--no-abbrev",
                            "--column=<options>",
                            "--no-column",
                            "--sort=<key>",
                            "--merged <commit>",
                            "--no-merged <commit>",
                            "--contains <commit>",
                            "--no-contains <commit>",
                            "--points-at <object>",
                            "--format=<format>",
                            "-r",
                            "--remotes",
                            "-a",
                            "--all",
                            "--list",
                        ],
                        fullCommand: "",
                        guide: "Hello World"
                    }
                ]
            }
        }
    }
}
</script>