<component
    class="c-notifications"
    :class="{'t-res-notifications': notifications.length, 't-nores-notifications': !notifications.length}"
>
    <transition-group name="notification" tag="ul">
        <li
            v-for="item in notifications"
            v-bind:key="notifications.indexOf(item)"
            class="notification"
            :class="classes('notification', item)"
        >
            <div class="icon">
                <icon :name="item.icon" v-if="item.icon"/>
            </div>
            <div class="message cf">
                {{item.message}}
                <span class="cf link" v-if="item.link" @click="openUrl(item.link.url)">{{item.link.text}}</span>
            </div>
        </li>
    </transition-group>
</component>
