<script setup>
import {
  Card,
  CardContent,
  CardDescription,
  CardFooter,
  CardHeader,
  CardTitle,
} from "@/components/ui/card";
import { Input } from "@/components/ui/input";
import { Label } from "@/components/ui/label";
import { Tabs, TabsContent, TabsList, TabsTrigger } from "@/components/ui/tabs";
import {
  Carousel,
  CarouselContent,
  CarouselItem,
  CarouselNext,
  CarouselPrevious,
} from "@/components/ui/carousel";
import {
  Dialog,
  DialogContent,
  DialogHeader,
  DialogTitle,
  DialogDescription,
} from "@/components/ui/dialog";
import { ref } from "vue";

import projects from "@/data/projects.json";

const data = projects.map((x) => ({
  ...x,
}));

const showImage = ref(false);
const selectedImage = ref("");
const openImage = (img) => {
  selectedImage.value = img;
  showImage.value = true;
};

console.log(data);
</script>

<template>
  <div class="flex flex-col items-center justify-center mt-6">
    <div class="font-bold text-5xl">My Projects</div>
    <div>Here are some of the projects I’ve worked on.</div>
    <div class="flex w-full flex-col gap-6 justify-center">
      <Tabs defaultValue="ifca">
        <TabsList>
          <TabsTrigger value="ifca">IFCA Software</TabsTrigger>
        </TabsList>

        <TabsContent value="ifca">
          <Tabs :defaultValue="data[0].project_name">
            <TabsList class="w-full flex flex-wrap gap-2 justify-start">
              <TabsTrigger
                v-for="project in data"
                :key="project.project_name"
                :value="project.project_name"
                class="px-4 py-2"
              >
                {{ project.project_name }}
              </TabsTrigger>
            </TabsList>

            <TabsContent
              v-for="project in data"
              :key="project.project_name"
              :value="project.project_name"
            >
              <Card>
                <CardHeader>
                  <CardTitle>{{ project.project_name }}</CardTitle>
                  <CardDescription>
                    {{ project.description }}
                  </CardDescription>
                </CardHeader>

                <CardContent class="grid gap-6">
                  <div class="flex gap-4 flex-wrap">
                    <Carousel class="w-full">
                      <CarouselContent>
                        <CarouselItem
                          v-for="(img, index) in project.images"
                          :key="index"
                        >
                          <div class="p-1">
                            <Card>
                              <CardContent
                                class="flex items-center justify-center p-0"
                              >
                                <img
                                  :src="img"
                                  :alt="project.project_name"
                                  class="w-full h-full object-cover rounded-xl cursor-pointer"
                                  @click="openImage(img)"
                                />
                              </CardContent>
                            </Card>
                          </div>
                        </CarouselItem>
                      </CarouselContent>

                      <CarouselPrevious />
                      <CarouselNext />
                    </Carousel>
                  </div>
                </CardContent>
              </Card>
            </TabsContent>
          </Tabs>
        </TabsContent>
      </Tabs>
    </div>
  </div>
  <Dialog v-model:open="showImage">
    <DialogContent class="max-w-7xl p-0 bg-transparent border-none shadow-none">
      <img
        :src="selectedImage"
        alt="Preview"
        class="rounded-xl w-full h-full object-contain"
      />
    </DialogContent>
  </Dialog>
</template>
